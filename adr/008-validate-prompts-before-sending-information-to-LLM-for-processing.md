---
title: Prompt Validation prior to sending information for LLM processing
authors:
  - Ryan Hertzog
date_created: 02/17/2025
last_updated: 02/18/2025
---

## Status

- Proposed: 02/17/2025
- Accepted: 02/18/2025

## Participants

- Brandon Moriarty
- Chris Acton
- Megin Mathew
- Jagreet Atwal
- Ryan Hertzog

## Context

- Our AI grading system relies on a Large Language Model (LLM) to process and evaluate candidate responses.
- To ensure the accuracy, relevance, and security of the information sent to the LLM, we need a mechanism for validating prompts before they are processed.
- Prompt validation helps prevent errors, maintain data integrity, and ensure that the LLM receives well-formed and contextually appropriate inputs.

## Decision

- We have decided to implement prompt validation prior to sending information to our selected LLM for processing. This validation step will ensure that all prompts are accurate, relevant, and secure before being processed by the LLM.

## Consequences

### Pros

- Improved Accuracy:
  - Error Prevention: Validating prompts helps prevent errors and ensures that the LLM receives accurate and well-formed inputs.
  - Relevance Check: Ensures that the prompts are contextually relevant and aligned with the intended evaluation criteria.
- Data Integrity:
  - Consistency: Maintains the integrity and consistency of the data being processed by the LLM.
  - Validation Rules: Applies predefined validation rules to ensure that all prompts meet the required standards.
- Security:
  - Input Sanitization: Validates and sanitizes inputs to prevent the injection of malicious or harmful content.
  - Compliance: Ensures compliance with data security and privacy regulations by validating the content before processing.
- Enhanced Performance:
  - Efficient Processing: Reduces the likelihood of processing invalid or irrelevant prompts, improving the overall efficiency of the LLM.
  - Resource Optimization: Optimizes the use of computational resources by ensuring that only valid and relevant prompts are processed.
- User Experience:
  - Clear Feedback: Provides clear feedback to users if their inputs do not meet the validation criteria, helping them correct and resubmit their prompts.
  - Trust and Reliability: Increases trust and reliability in the system by ensuring that the LLM processes high-quality inputs.

### Cons

- Implementation Effort:
  - Development Time: Implementing prompt validation requires additional development time and effort.
  - Complexity: Adds complexity to the system architecture, requiring careful design and integration.
- Performance Overhead:
  - Validation Step: Introducing a validation step may add a slight performance overhead, potentially increasing the time required to process prompts.
  - Resource Utilization: Requires additional computational resources to perform validation checks.
- Maintenance:
  - Ongoing Updates: Validation rules and criteria may need to be updated regularly to adapt to new requirements and changes in the dataset.
  - Monitoring: Requires continuous monitoring to ensure that the validation process remains effective and up-to-date.
