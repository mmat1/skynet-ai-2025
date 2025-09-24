# Troubleshooting Guide - Skynet AI

This document provides solutions to common issues encountered when deploying and operating the Skynet AI system.

## Infrastructure and Deployment Issues

### Terraform Output Processing Error

**Error Message:**
```
Error: Unable to process file command 'output' successfully.
Error: Invalid format 'blobfuncdev-func-omsj02::debug::Terraform exited with code 0.'
```

**Root Cause:**
This error occurs when a deployment or CI/CD system is attempting to parse Terraform output but encounters an unexpected format. The key issue is that "Terraform exited with code 0" is actually a success message (exit code 0 = success), but the parser is treating it as an error due to incorrect format expectations.

**Resolution Steps:**

1. **Verify Terraform Output Format**
   - Check that your Terraform commands are outputting in the expected format (JSON, plain text, etc.)
   - Ensure any wrapper scripts properly handle Terraform's success messages

2. **Update Output Parser**
   - Modify the file processing logic to correctly interpret exit code 0 as success
   - Add proper handling for debug messages in the format: `{resource}::debug::{message}`

3. **Example Fix for Output Processing:**
   ```bash
   # Instead of treating any output as an error, check the actual exit code
   terraform_output=$(terraform apply -auto-approve 2>&1)
   terraform_exit_code=$?
   
   if [ $terraform_exit_code -eq 0 ]; then
       echo "Terraform executed successfully"
       # Process the output normally
   else
       echo "Terraform failed with exit code: $terraform_exit_code"
       echo "Output: $terraform_output"
   fi
   ```

4. **Debug Message Filtering**
   - Filter out debug messages that contain "::debug::" prefix
   - Focus on actual error messages that don't contain "exited with code 0"

**Prevention:**
- Always check exit codes rather than parsing output text for error detection
- Implement proper logging levels (debug, info, error) in deployment scripts
- Use structured output formats (JSON) when possible for easier parsing

**Related Resources:**
- [Terraform Output Documentation](https://www.terraform.io/docs/configuration/outputs.html)
- [System Overview](system-overview.md)
- [Architecture Decision Records](adr/)

---

## Additional Common Issues

*This section will be expanded as more issues are identified and resolved.*