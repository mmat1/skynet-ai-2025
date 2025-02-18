---
title: Create an Index per Question and Version for Short Answer Vector Database
authors:
  - Ryan Hertzog
  - Megin Mathew
  - Jagreet Atwal
  - Brandon Moriarty
  - Chris Acton
date_created: 02/14/2025
last_updated: 02/18/2025
---

## Status

- Proposed: 02/14/2025
- Accepted: 02/14/2025

## Participants

- Brandon Moriarty
- Chris Acton
- Megin Mathew
- Jagreet Atwal
- Ryan Hertzog

## Context

The SoftArchCert system requires an efficient and scalable indexing strategy for storing and retrieving embeddings of questions and answers. The indexing strategy must support various versions of questions and answers, ensuring quick and accurate retrieval for AI grading and analysis.

## Decision

- We will use an indexing strategy where each question and its versions are stored in separate indices. This approach ensures that each version of a question can be independently managed and retrieved, providing flexibility and scalability.
  - Scalability: Each version of a question can be independently indexed, updated, and deleted without affecting other versions.
  - Performance: Ensures efficient retrieval of specific questions and versions, reducing the overhead of managing large indexes.
  - Flexibility: Allows for easy rollback to previous versions if needed, providing better control over the data.
- Each question will have a unique index for each version.
- The indices will be named using a convention that includes the question Id and version number (e.g., question_1_v1, question_1_v2).
- The system will include mechanisms to create, update, and delete indices as needed.

## Consequences

- Storage Costs: The number of indexes will increase, leading to higher storage costs. However, this is offset by the benefits of improved performance and manageability.
- Complexity: The system will need to manage multiple indexes, but this complexity is justified by the advantages in scalability and flexibility.

## Other Considerations:

### Single Index for All Questions and Versions:

**Pros**: Simplifies the indexing structure.
**Cons**: Requires rebuilding the entire index for any changes, leading to high maintenance costs and potential performance issues.

### Index per Question with All Versions:

**Pros**: Allows for version management within a single index.
**Cons**: Can lead to large index sizes and complexity in managing multiple versions within the same index.

### Index per Question and Version:

**Pros**: Provides clear separation of versions, simplifies management, and allows for independent updates and deletions.
**Cons**: Increases the number of indexes, which may lead to higher storage costs.

### Parent-Child Relationship for Questions and Versions:

**Pros**: Reduces data duplication by storing common information at the parent level.
**Cons**: Adds complexity in managing relationships and querying data.
