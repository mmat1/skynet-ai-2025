---
title: Store expert graders AI feedback to be used for adjustments / tuning to answer key database
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

- Our AI grading system for short answer questions involves both AI and expert graders to ensure high accuracy and reliability.
- Expert graders review AI-graded exams, provide feedback, and make adjustments to the AI-assigned grades.
- To continuously improve the system's performance, we need to store this expert feedback and use it to adjust and tune the answer key database, which includes approved answers, grading criteria, and prompts.

## Decision

- We have decided to store expert grader AI review/feedback and use it for adjustments and tuning to the answer key database.
- This feedback will be systematically collected, analyzed, and applied to refine the AI's algorithms, prompts, and acceptable answers.

## Consequences

### Pros

- Continuous Improvement:
  - AI Refinement: Expert feedback provides valuable insights that can be used to refine and improve the AI's grading algorithms, leading to more accurate and reliable evaluations.
  - Adaptive Learning: The system can adapt and learn from expert feedback, continuously enhancing its performance and effectiveness.
- Enhanced Accuracy:
  - Quality Adjustments: Using expert feedback to adjust the answer key database ensures that the grading criteria and acceptable answers are up-to-date and accurate.
  - Error Correction: Identifies and corrects any discrepancies or errors in the AI's grading, improving overall accuracy.
- Comprehensive Feedback:
  - Detailed Insights: Storing expert feedback allows for a comprehensive analysis of the AI's performance, providing detailed insights into areas for improvement.
  - Actionable Data: Enables the generation of actionable data that can be used to fine-tune the system's prompts and grading criteria.
- Consistency and Reliability:
  - Standardized Adjustments: Ensures that adjustments to the answer key database are based on standardized and validated expert feedback, maintaining consistency and reliability.
  - Trust and Credibility: Increases trust and credibility in the AI-driven grading system by incorporating human expertise and oversight.

### Cons

- Resource Requirements:
  - Data Management: Storing and managing expert feedback requires additional data management resources and infrastructure.
  - Analysis Effort: Analyzing and applying expert feedback to adjust the answer key database requires ongoing effort and expertise.
- Complexity:
  - Integration Effort: Integrating expert feedback into the AI system adds complexity to the workflow and requires careful design and implementation.
  - Coordination Overhead: Managing the coordination between AI grading, expert review, and feedback integration can add to the system's operational complexity.
- Cost Implications:
  - Additional Costs: Involving expert graders and storing their feedback may incur additional costs related to human resources and data storage.
  - Infrastructure: May require additional infrastructure to support the storage, analysis, and application of expert feedback.
