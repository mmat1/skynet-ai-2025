---
title: Split candidate aptitude test submission data by question for storage
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
- Our AI grading system is designed to manage and evaluate candidate exams, providing detailed feedback and analytics.
- We need an efficient and scalable way to store and retrieve exam data to support various functionalities, including grading, feedback generation, performance analysis, and versioning of data such as questions and answers.

## Decision

- We will store candidate exam records per question as it aligns with our goals of granular analysis, efficient retrieval, scalability, flexibility, enhanced feedback, improved reporting, and ability to handle versioning of data such as questions and answers.

## Consequences

### Pros

- Granular Analysis:
  - Detailed Insights: Allows for more detailed analysis of candidate performance on individual questions.
  - Targeted Feedback: Enables the provision of specific feedback on strengths and weaknesses.
- Efficient Retrieval:
  - Faster Access: Facilitates quicker retrieval of individual responses for grading and feedback.
  - Focused Evaluation: Simplifies the process of evaluating specific questions without processing entire exams.
- Scalability:
  - Handles Growth: Scales better with increasing numbers of candidates and exams.
  - Performance: Maintains performance levels as data volume grows.
- Flexibility:
  - Easy Updates: Allows for easy updates and modifications to specific questions.
  - Adaptable Analysis: Provides flexibility in analyzing and managing data at a granular level.
- Enhanced Feedback:
  - Specific Guidance: Offers more detailed and specific feedback to candidates.
  - Improved Learning: Helps candidates understand their performance on individual questions.
- Improved Reporting:
  - Detailed Reports: Facilitates the generation of detailed reports and analytics.
  - Trend Analysis: Enables the identification of trends and common errors at a granular level.

### Cons

- Data Integrity:
  - Consistency Challenges: Ensuring data integrity and consistency across multiple question records can be complex.
  - Robust Mechanisms Needed: Requires robust mechanisms to maintain data integrity.
- Storage Overhead:
  - Increased Records: May increase storage overhead due to a higher number of records.
  - Optimization Required: Needs optimized storage strategies to manage overhead effectively.
- Complexity:
  - Data Management: Introduces additional complexity in data management and retrieval.
  - Efficient Access Patterns: Requires the development of efficient data access patterns and indexing strategies.
- Implementation Effort:
  - Development Time: May require additional development time to implement and optimize.
  - Resource Allocation: Needs careful resource allocation to handle the increased complexity and storage requirements.
