---
title: Handle Infrastructure Deployment Errors and Terraform Output Parsing
authors:
  - Copilot
date_created: 09/24/2025
last_updated: 09/24/2025
---

## Status

- Proposed: 09/24/2025
- Accepted: 09/24/2025

## Participants

- Copilot
- System Administrators
- DevOps Engineers

## Context

During deployment and infrastructure provisioning for the Skynet AI system, errors can occur when processing Terraform output and deployment logs. A specific issue has been identified:

```
Error: Unable to process file command 'output' successfully.
Error: Invalid format 'blobfuncdev-func-omsj02::debug::Terraform exited with code 0.'
```

This error indicates that:
1. A file processing command is attempting to parse Terraform output
2. The parser is incorrectly interpreting a success message (exit code 0) as an error
3. Debug messages with the format `{resource}::debug::{message}` are not being handled properly

The root cause is that deployment scripts are using text-based parsing of output instead of proper exit code checking, leading to false positive errors when Terraform actually succeeds.

## Decision

We have decided to implement proper error handling and output parsing for infrastructure deployment processes:

### 1. Exit Code Based Error Detection
- Always check actual exit codes rather than parsing output text for error detection
- Terraform exit code 0 = success, non-zero = failure
- Implement proper error handling that distinguishes between actual errors and success messages

### 2. Structured Output Processing
- Use structured formats (JSON) for Terraform output when possible
- Implement proper parsing logic that can handle debug messages and resource identifiers
- Filter out debug messages that use the `::debug::` format prefix

### 3. Logging Standards
- Implement consistent logging levels (debug, info, warn, error)
- Separate debug output from error reporting
- Use structured logging for easier parsing and analysis

### 4. Error Message Standardization
- Create clear, actionable error messages
- Include context about what failed and potential resolution steps
- Distinguish between transient and permanent failures

## Implementation Guidelines

### Terraform Output Processing Example
```bash
# Correct approach: Check exit code first
terraform_output=$(terraform apply -auto-approve 2>&1)
terraform_exit_code=$?

if [ $terraform_exit_code -eq 0 ]; then
    echo "Terraform executed successfully"
    # Process output for information extraction
    echo "$terraform_output" | grep -v "::debug::" | jq -r '.outputs'
else
    echo "ERROR: Terraform failed with exit code: $terraform_exit_code"
    echo "Output: $terraform_output"
    exit 1
fi
```

### Output Parser Implementation
```bash
# Function to parse deployment output safely
parse_deployment_output() {
    local output="$1"
    local exit_code="$2"
    
    # Check exit code first
    if [ $exit_code -ne 0 ]; then
        echo "ERROR: Deployment failed with exit code: $exit_code"
        return 1
    fi
    
    # Filter debug messages and extract useful information
    filtered_output=$(echo "$output" | grep -v "::debug::" | grep -v "exited with code 0")
    
    # Process the filtered output
    echo "Deployment successful. Filtered output: $filtered_output"
    return 0
}
```

## Consequences

### Pros

- **Accurate Error Detection**: Eliminates false positive errors caused by misinterpreting success messages
- **Improved Reliability**: Proper exit code checking ensures accurate deployment status
- **Better Debugging**: Structured logging and output parsing makes troubleshooting easier
- **Reduced Manual Intervention**: Fewer false alarms requiring manual investigation
- **Standardized Error Handling**: Consistent approach across all deployment processes

### Cons

- **Initial Implementation Effort**: Requires updating existing deployment scripts
- **Additional Complexity**: More sophisticated parsing logic needed
- **Testing Requirements**: Need to test various output scenarios and edge cases

## Related ADRs

- [019 - Use existing databases to measure observability metrics](019-use-existing-databases-to-measure-observability-metrics.md)
- [020 - Build dashboard for SLO/SLA for AI services](020-build-dashboard-for-SLO-SLA-for-AI-services.md)

## References

- [Troubleshooting Guide](../troubleshooting.md)
- [System Overview](../system-overview.md)
- [Terraform Documentation](https://www.terraform.io/docs/)