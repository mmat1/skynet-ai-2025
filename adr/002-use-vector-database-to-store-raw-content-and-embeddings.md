---
title: Use a Vector Database, for Aptitude Test (Test 1), to index and store embeddings and raw content together
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

- Certifiable Inc requires candidates of their SoftArchCert to take an aptitude test which includes multiple choice and short answer questions.
- A question and answer key will be required to determine if a candidates response is correct.
- In a Retrieval-Augmented Generation (RAG) system, both the embeddings and the original content are typically stored. Here's why
  - Embeddings: These are numerical representations of the content that capture its semantic meaning. They are used for efficient similarity searches and retrieval of relevant information.
  - Original Content: While embeddings are great for finding relevant pieces of information, the actual content is needed to provide context and detailed responses. Once relevant embeddings are retrieved, the original content associated with those embeddings is used to generate a coherent and contextually accurate response
- Many modern Vector Databases natively support storing of both embeddings and raw content used to produce the embeddings, which can simplify retrieval and improve efficiency.

## Decision

- We have decided to use a Vector Database with native support for storing both embeddings and raw content for our AI-driven grading system for short answer questions.

## Consequences

### Pros

- Simplified Retrieval:
  - Efficiency: Storing both embeddings and raw content in the same database simplifies the retrieval process, reducing the need for multiple queries and data transfers.
  - Consistency: Ensures that embeddings and their corresponding content are always aligned, minimizing the risk of inconsistencies.
- Performance:
  - Speed: Integrated storage can improve the speed of similarity searches and content retrieval, leading to faster response times.
  - Optimization: Vector databases are optimized for handling high-dimensional data, ensuring efficient storage and retrieval operations.
- Ease of Management:
  - Single System: Managing a single database system for both embeddings and content reduces the complexity of the architecture.
  - Maintenance: Simplifies maintenance tasks, such as backups, updates, and scaling, as everything is contained within one system.
- Scalability:
  - Horizontal Scaling: Many vector databases are designed to scale horizontally, allowing for efficient handling of large volumes of data and queries.
  - Flexibility: Supports the growth of the dataset and the increasing demand for similarity searches without significant performance degradation.
- Enhanced Capabilities:
  - Hybrid Search: Combines vector search with traditional metadata filters and other query capabilities, providing powerful hybrid search functionalities.
  - Advanced Features: Some vector databases offer additional features like graph lookups, aggregation pipelines, and more, enhancing the overall capabilities of the system.

### Cons

- Resource Requirements:
  - Computational Load: Vector databases can be resource-intensive, requiring significant computational power for indexing and querying high-dimensional data.
  - Storage Costs: Storing both embeddings and raw content in the same database can increase storage costs, especially for large datasets.
- Complexity:
  - Learning Curve: Implementing and optimizing a vector database may require specialized knowledge and skills, leading to a steeper learning curve for the development team.
  - Integration: Integrating a vector database with existing systems and workflows may require additional development effort and coordination.
- Maintenance Overhead:
  - Updates and Upgrades: Keeping the vector database up-to-date with the latest features and security patches can add to the maintenance overhead.
  - Monitoring: Continuous monitoring and optimization may be necessary to ensure optimal performance and reliability.
