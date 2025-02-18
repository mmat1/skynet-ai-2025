---
title: Applying embedding model before storing data to Vector Database
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

- Certifiable Inc will need to manage incremental updates and new exam questions, answers, and grading criteria for a variety of reasons such as, new technology emerges, technology is phased out, questions are retired or deemed no longer relevant, historical analysis, etc.
- As our datasets evolve and change over time, it is crucial to maintain the accuracy, consistency, and relevance of our embeddings and indexes. To achieve this, we need a strategy for versioning both the index and embeddings.
- This will also allow us to gain insights into the effects of data changes, and ensures that embeddings are aligned with the current state of the dataset. This improves the accuracy of similarity searches and evaluations, leading to more reliable grading and feedback.

## Decision

- We have decided to implement a versioning system for our index and embeddings to ensure that as datasets evolve, we can maintain consistency, track changes, and manage updates effectively.

## Consequences

### Pros

- Consistency:
  - Aligned Data: Versioning ensures that embeddings and indexes are consistently aligned with the current state of the dataset.
  - Reduced Discrepancies: Minimizes discrepancies between different versions of the data, embeddings, and indexes.
- Traceability:
  - Change Tracking: Allows us to track changes and updates to the dataset, embeddings, and indexes over time.
  - Auditability: Provides a clear audit trail of modifications, enabling us to understand the evolution of the data and its impact on the system.
- Flexibility:
  - Rollback Capability: Enables us to roll back to previous versions of embeddings and indexes if needed, ensuring system stability and reliability.
  - Parallel Versions: Supports the use of multiple versions of embeddings and indexes simultaneously, facilitating A/B testing and gradual rollouts.
- Improved Accuracy:
  - Up-to-date Embeddings: Ensures that embeddings are regularly updated to reflect the latest state of the dataset, improving the accuracy of similarity searches and evaluations.
  - Optimized Indexes: Keeps indexes optimized for the current data, enhancing retrieval performance and efficiency.
- Scalability:
  - Efficient Updates: Facilitates efficient updates and management of large datasets, ensuring that the system can scale effectively as data volumes grow.
  - Resource Management: Allows for better resource allocation by managing different versions of embeddings and indexes.

### Cons

- Complexity:
  - Implementation Effort: Implementing a versioning system adds complexity to the architecture and requires additional development effort.
  - Maintenance Overhead: Maintaining multiple versions of embeddings and indexes can increase the maintenance overhead.
- Storage Requirements:
  - Increased Storage: Storing multiple versions of embeddings and indexes requires additional storage space, potentially increasing costs.
  - Optimization Needed: Requires optimized storage strategies to manage the increased storage requirements effectively.
- Performance Impact:
  - Version Management: Managing and switching between different versions of embeddings and indexes can impact system performance if not handled efficiently.
  - Resource Allocation: Allocating resources to maintain and update multiple versions may affect the overall system performance.
