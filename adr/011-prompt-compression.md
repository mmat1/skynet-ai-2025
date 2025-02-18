---
title: Use Prompt Compression
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

Certifiable Inc. has concerns about the potential high costs associated with AI, especially given the anticipated 5-10X increase in certification requests. 

## Decision

We will implement prompt compression when inputting prompts to the LLM. 

## Consequences

### Cost Efficiency

- By using prompt compression, the company can significantly reduce the computational resources required, leading to lower operational costs.

- Smaller prompts require less processing power, which means fewer CPU/GPU cycles are needed. This directly translates to lower energy consumption and reduced wear on hardware for on-prem solutions.

- Reducing the computational load can lead to lower cloud usage fees. 

- Compressed prompts use less memory, which can reduce the need for expensive high-memory instances or servers. This efficiency helps in managing costs associated with memory-intensive operations.

- With quicker processing times, the system can handle more requests in the same amount of time, improving throughput. This efficiency can reduce the need for additional infrastructure to manage peak loads, thereby saving costs.

- Optimized Resource Allocation: By using resources more efficiently, the system can allocate computational power where it's most needed, avoiding over-provisioning and under-utilization, which can be costly.

### Scalability 

- The solution will be better equipped to handle the increased volume of certification requests, ensuring that the system remains responsive and efficient.

- By compressing prompts, the AI model processes smaller inputs, which requires less computational power. This reduction in resource usage allows the system to handle more requests simultaneously.

- Smaller prompts mean quicker processing times for each request. This speed increase enables the system to manage a higher volume of requests in a given time frame.