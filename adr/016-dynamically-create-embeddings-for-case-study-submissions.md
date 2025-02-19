---
title: Dynamically create embeddings for candidate Case Study submissions
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

- Our AI grading system evaluates candidate case study architecture submissions.
- We need to decide whether to pre-create embeddings for these submissions or generate them dynamically during the evaluation process.
- Pre-creating embeddings can improve efficiency but may not always be necessary.
- We need to consider the trade-offs and determine the best approach for our system.

## Decision

- We have decided not to pre-create embeddings for candidate Case Study submissions. Instead, we will generate embeddings dynamically during the evaluation process.
- As an alternative option, if the data is too large for candidate Case Study submissions, we can elect to create embeddings ahead of time and store them in a VectorDB.

## Consequences

### Pros

- Flexibility:
  - Dynamic Processing: Generating embeddings dynamically allows for more flexibility in handling diverse and evolving candidate submissions.
  - Adaptability: The system can adapt to new and unique submissions without the need for pre-processing.
- Resource Management:
  - Optimized Use: Avoids the upfront computational and storage costs associated with pre-creating embeddings for all submissions.
  - On-Demand Processing: Resources are allocated on-demand, reducing the overall computational load.
- Simplicity:
  - Simplified Workflow: Eliminates the need for a separate pre-processing step, simplifying the overall workflow.
  - Reduced Maintenance: Reduces the maintenance overhead associated with managing pre-created embeddings.
- Real-Time Adaptation:
  - Contextual Relevance: Dynamic embedding generation ensures that embeddings are contextually relevant to the specific evaluation criteria and current state of the system.
  - Immediate Updates: Any updates or improvements to the embedding model are immediately reflected in the generated embeddings.

### Cons

- Performance Impact:
  - Increased Latency: Generating embeddings dynamically may introduce latency, potentially slowing down the evaluation process.
  - Higher Computational Load: Real-time embedding generation requires significant computational resources, which may impact system performance.
- Scalability Challenges:
  - Handling Large Volumes: Scaling the system to handle large volumes of candidate submissions may be challenging due to the computational demands of dynamic embedding generation.
  - Resource Allocation: Requires careful resource allocation to ensure that the system can handle peak loads efficiently.
- Alternative Option:
  - Pre-creating Embeddings: If the data is too large for candidate Case Study submissions, we can elect to create embeddings ahead of time and store them in a VectorDB. This approach can improve efficiency for large datasets but may require additional storage and pre-processing resources.
