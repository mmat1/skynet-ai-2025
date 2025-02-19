---
title: Store AI Graded Candidate Exams as a single ready to review record
authors:
  - Ryan Hertzog
date_created: 02/19/2025
last_updated: 02/19/2025
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

- Our AI grading system processes each question individually using a Large Language Model (LLM) to ensure accurate and detailed evaluation.
- After processing, we need to store the graded responses in a way that maintains the integrity and coherence of the entire exam.
- To achieve this, we need to decide on the best approach for storing the AI-graded candidate exams.

## Decision

- We have decided to store AI-graded candidate exams as a single record, merging the individually processed questions back together into a cohesive exam record. Refer to [ADR 008](/adr/008-LLM-will-evaluate-and-grade-one-question-at-a-time.md) for details on LLM evaluation and grading one question at a time.

## Consequences

### Pros

- Coherence and Integrity:
  - Unified Record: Storing the entire exam as a single record ensures that all graded responses are kept together, maintaining the coherence and integrity of the exam.
  - Context Preservation: Preserves the context of the exam, allowing for a holistic view of the candidate's performance.
- Simplified Retrieval:
  - Efficient Access: Facilitates efficient retrieval of the entire exam record, making it easier to review and analyze the candidate's performance.
  - Streamlined Workflow: Simplifies the workflow by consolidating all responses into a single record, reducing the complexity of managing multiple records.
- Enhanced Feedback:
  - Comprehensive Feedback: Enables the generation of comprehensive feedback for the entire exam, providing candidates with a complete overview of their performance.
  - Detailed Analysis: Allows for detailed analysis and reporting on the candidate's performance across all questions.
- Consistency:
  - Uniform Storage: Ensures that all exams are stored in a consistent format, making it easier to manage and maintain the database.
  - Standardized Processing: Standardizes the processing and storage of graded exams, ensuring uniformity across the system.

### Cons

- Storage Overhead:
  - Larger Records: Storing entire exams as single records may increase the storage overhead, especially for exams with a large number of questions.
  - Optimization Needed: Requires optimized storage strategies to manage the increased size of the records effectively.
- Complexity in Merging:
  - Merging Process: Merging individually processed questions back into a single record adds complexity to the system.
  - Coordination Overhead: Requires careful coordination to ensure that all responses are accurately merged and stored.
    -Resource Utilization:
  - Computational Load: The process of merging and storing large records may require additional computational resources.
  - Efficiency Trade-offs: May trade off some efficiency for the benefits of coherence and comprehensive feedback.
