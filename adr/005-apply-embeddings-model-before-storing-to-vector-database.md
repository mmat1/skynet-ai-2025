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

- Our AI grading system for short answer questions requires efficient storage, retrieval, and processing of large volumes of data. To achieve this, we need to decide on the best approach for generating embeddings, which are crucial for similarity searches and content retrieval. The two primary options are:
  - Pre-processing Data and Applying Embeddings: This involves converting raw content into embeddings before storing it in our vector database. The embeddings are pre-computed and stored alongside the raw content, allowing for efficient retrieval and processing.
  - Using an LLM to Apply Embeddings: This approach involves using a Large Language Model (LLM) to generate embeddings dynamically in real-time based on user queries. The LLM processes the raw content and generates embeddings on-the-fly, providing contextually relevant representations.

## Decision

- We have decided to apply the embedding model to our exam question and answer data before storing it in a Vector Database.
  - By pre-processing data and applying embeddings, we can achieve greater efficiency, resource optimization, consistency, and simplified workflow, making it a preferred approach for our AI grading system.

## Consequences

### Pros

- Consistency:
  - Aligned Understanding: Using the same embedding model as the LLM ensures that the embeddings are consistent with the LLM's understanding of the content.
  - Reduced Discrepancies: Minimizes discrepancies between the embeddings and the LLM's processing, leading to more accurate and relevant results.
- Efficiency:
  - Faster Retrieval: Pre-computed embeddings allow for faster similarity searches and retrieval operations in the vector database.
  - Optimized Storage: Embeddings provide a compact representation of the content, optimizing storage space and reducing data redundancy.
- Performance:
  - Improved Accuracy: High-quality embeddings enhance the accuracy of similarity searches, leading to better evaluation and feedback generation.
  - Scalability: The system can handle large volumes of data more efficiently, as embeddings are easier to manage and process.
- Simplified Workflow:
  - Streamlined Processing: Applying the embedding model before storage simplifies the workflow, as the data is already in a format suitable for similarity searches and retrieval.
  - Consistency in Processing: Ensures that all data is processed uniformly, maintaining consistency across the system.

### Cons

- Resource Requirements:
  - Computational Load: Applying the embedding model to large volumes of data requires significant computational resources.
  - Initial Overhead: The initial process of converting raw content into embeddings can be resource-intensive and time-consuming.
- Complexity:
  - Implementation Effort: Implementing and optimizing the embedding process requires additional development effort and expertise.
  - Maintenance: Maintaining the embedding model and ensuring it stays up-to-date with the LLM can add to the system's complexity.
- Dependency on Embedding Quality:
  - Model Quality: The quality of the embeddings is crucial for the system's overall performance. Any issues with the embedding model can impact the accuracy of similarity searches and evaluations.
  - Model Updates: Regular updates to the embedding model may be necessary to maintain high-quality embeddings, requiring ongoing monitoring and adjustments.
