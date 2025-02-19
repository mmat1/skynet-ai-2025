---
title: Use existing databases to measure Observability metrics
authors:
  - Ryan Hertzog
date_created: 02/19/2025
last_updated: 02/19/2025
---

## Status

- Proposed: 02/19/2025
- Accepted: 02/19/2025

## Participants

- Brandon Moriarty
- Chris Acton
- Megin Mathew
- Jagreet Atwal
- Ryan Hertzog

## Context

- Our AI grading system involves multiple databases throughout the candidate exam process, including registration, aptitude test and case study submissions databases, vector database, AI graded database, expert review and graded databases, and feedback databases.
- To ensure we have observability built into our system, we need to measure various metrics such as performance, accuracy, and system health.
- We need to decide whether to use existing databases to measure these observability metrics or create a separate database/store for this purpose.

## Decision

- We have decided to use existing databases to measure observability metrics instead of creating a separate database/store. This approach leverages the data already being collected and stored across various databases involved in the candidate exam process.

## Consequences

### Pros

- Resource Efficiency:
  - Cost Savings: Avoids the additional costs associated with setting up and maintaining a separate database/store for observability metrics.
  - Utilization of Existing Infrastructure: Leverages the existing database infrastructure, reducing the need for additional resources and hardware.
- Simplified Architecture:
  - Reduced Complexity: Simplifies the system architecture by avoiding the introduction of a new database/store, making it easier to manage and maintain.
  - Streamlined Data Flow: Ensures a more streamlined data flow by using existing databases, reducing the need for data duplication and synchronization.
- Comprehensive Observability:
  - Holistic View: Provides a holistic view of the system's performance and health by integrating observability metrics with existing data sources.
  - Contextual Insights: Allows for more contextual insights by correlating observability metrics with operational data from various stages of the candidate exam process.
- Faster Implementation:
  - Quick Deployment: Enables faster implementation of observability metrics by utilizing existing databases, reducing the time required for setup and configuration.
  - Immediate Benefits: Provides immediate benefits by leveraging the data already being collected, allowing for quicker identification and resolution of issues.

### Cons

- Data Overhead:
  - Increased Load: Adding observability metrics to existing databases may increase the load on these databases, potentially impacting performance.
  - Storage Requirements: May require additional storage capacity to accommodate the observability metrics, leading to increased storage costs.
- Complexity in Querying:
  - Complex Queries: Integrating observability metrics with existing data may result in more complex queries, requiring careful optimization to ensure efficient performance.
  - Data Integration: Ensuring seamless integration of observability metrics with existing data sources may require additional effort and expertise.
- Potential for Data Contention:
  - Resource Contention: Increased read/write operations for observability metrics may lead to resource contention, affecting the performance of operational queries.
  - Performance Impact: Requires careful monitoring and management to ensure that the addition of observability metrics does not negatively impact the overall system performance.
