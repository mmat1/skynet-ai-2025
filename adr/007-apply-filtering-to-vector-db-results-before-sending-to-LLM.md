---
title: Apply filtering to Vector DB query to return top results for Short Answers
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

- Our AI-driven grading system for short answer questions relies on a Vector Database to store and retrieve embeddings and raw content including questions, approved answers, grading criteria, and other metadata.
- To ensure accurate and relevant grading, we need to refine the results retrieved from the Vector Database. Applying filtering to the top results can help improve the quality and relevance of the responses used for evaluation by our selected LLM.

## Decision

- We have decided to apply filtering to the top results retrieved from the VectorDB query for short answers. This filtering process will refine the results based on specific criteria to ensure that only the most relevant and accurate responses are used for grading by our selected LLM.

## Consequences

### Pros

- Improved Accuracy:
  - Relevance: Filtering ensures that only the most relevant results are considered, improving the accuracy of the grading process.
  - Quality: By applying specific criteria, we can ensure that the top results meet the quality standards required for accurate evaluation.
- Enhanced Feedback:
  - Specificity: Filtering allows us to provide more specific and detailed feedback to students, helping them understand their performance and areas for improvement.
  - Clarity: Ensures that the feedback is based on the most relevant and high-quality responses, making it clearer and more actionable for students.
- Efficiency:
  - Reduced Noise: Filtering reduces the noise in the results, making the grading process more efficient and focused.
  - Streamlined Processing: By narrowing down the results to the most relevant ones, we can streamline the processing and evaluation workflow.
- Consistency:
  - Uniform Criteria: Applying consistent filtering criteria ensures that all responses are evaluated uniformly, maintaining fairness and consistency in grading.
  - Standardization: Helps standardize the grading process, ensuring that all students are evaluated based on the same criteria.

### Cons

- Complexity:
  - Implementation Effort: Implementing filtering mechanisms adds complexity to the system and requires additional development effort.
  - Maintenance: Maintaining and updating the filtering criteria can add to the system's maintenance overhead.
- Resource Requirements:
  - Computational Load: Filtering the top results may require additional computational resources, potentially impacting system performance.
  - Optimization Needed: Requires careful optimization to ensure that the filtering process does not introduce significant latency.
- Potential for Over-filtering:
  - Exclusion Risk: There is a risk of over-filtering, where relevant results may be excluded if the criteria are too strict.
  - Balancing Act: Requires a careful balance between filtering out noise and retaining relevant results to ensure accurate grading.
