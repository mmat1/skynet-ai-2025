---
title: Use Prompt Compression before LLM processing
authors:
  - Brandon Moriarty
date_created: 02/18/2025
last_updated: 02/18/2025
---

## Status

- Proposed: 02/17/2025
- Accepted: 02/17/2025

## Participants

- Brandon Moriarty
- Chris Acton
- Megin Mathew
- Jagreet Atwal
- Ryan Hertzog

## Context

- Certifiable Inc. has concerns about the potential high costs associated with AI, especially given the anticipated 5-10X increase in certification requests.
- Our AI grading system relies on a Large Language Model (LLM) to process and evaluate candidate responses.
- Given the potential length and complexity of prompts, it is essential to optimize the input to ensure efficient and accurate processing.
- Prompt compression can help reduce the size of the input while preserving the essential information, leading to improved performance and reduced computational load.

## Decision

- We have decided to implement prompt compression before sending information to our selected LLM for processing. This approach will optimize the input size, ensuring efficient and accurate processing by the LLM.

## Consequences

### Pros

- Improved Efficiency:
  - Reduced Input Size: Compressing prompts reduces the size of the input, leading to faster processing times and lower latency.
  - Optimized Resource Use: Decreases the computational load on the LLM, optimizing the use of available resources.
- Enhanced Performance:
  - Faster Response: Smaller input sizes result in quicker response times, improving the overall performance of the grading system.
  - Scalability: Facilitates scalability by allowing the system to handle larger volumes of data without significant performance degradation.
- Cost Savings:
  - Lower Costs: Reducing the computational load can lead to cost savings, as fewer resources are required for processing compressed prompts.
  - Efficient Utilization: Ensures more efficient utilization of computational resources, potentially lowering operational costs.
- Maintained Accuracy:
  - Essential Information: Prompt compression techniques are designed to preserve the essential information, ensuring that the LLM can still accurately process and evaluate the input.
  - Context Preservation: Maintains the context and relevance of the input, ensuring accurate and meaningful responses from the LLM.

### Cons

- Implementation Effort:
  - Development Time: Implementing prompt compression requires additional development time and effort.
  - Complexity: Adds complexity to the system architecture, requiring careful design and integration.
- Potential Information Loss:
  - Compression Quality: If not implemented correctly, prompt compression may lead to the loss of important information, potentially affecting the accuracy of the LLM's responses.
  - Balancing Act: Requires a careful balance between reducing input size and preserving essential information to ensure accurate processing.
- Maintenance:
  - Ongoing Updates: Compression algorithms and techniques may need to be updated regularly to adapt to new requirements and changes in the dataset.
  - Monitoring: Requires continuous monitoring to ensure that the compression process remains effective and does not degrade over time.
