---
title: Allow expert graders to review AI-graded exams and provide feedback
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

- Our AI grading system processes and stores candidate exams as single records, with each question individually graded by a Large Language Model (LLM).
- To ensure the highest accuracy and reliability, we need a mechanism for expert graders to review the AI-graded exams, provide feedback, and make adjustments.
- This process will help refine the AI's performance, improve grading accuracy, and update the system's prompts and acceptable answer keys.

## Decision

- We have decided to allow expert graders to review AI-graded exams and provide feedback. Expert graders will be able to review the AI's responses, overwrite the AI-assigned grades per question, and provide feedback that will be used to update and adjust the AI, prompts, and acceptable answer keys.

## Consequences

### Pros

- Improved Accuracy:
  - Expert Validation: Expert graders can validate and correct AI-assigned grades, ensuring higher accuracy and reliability in the grading process.
  - Error Correction: Allows for the identification and correction of any errors made by the AI, improving overall grading quality.
- Enhanced Feedback:
  - Detailed Insights: Expert graders can provide detailed feedback on the AI's responses, offering valuable insights for both students and system improvement.
  - Actionable Guidance: Students receive more comprehensive and actionable feedback, helping them understand their performance and areas for improvement.
- Continuous Improvement:
  - AI Refinement: Feedback from expert graders can be used to refine and adjust the AI's algorithms, prompts, and acceptable answer keys, leading to continuous improvement in the system's performance.
  - Adaptive Learning: The system can adapt and learn from expert feedback, becoming more accurate and effective over time.
- Quality Assurance:
  - Consistency Checks: Expert review ensures consistency and fairness in grading, maintaining high standards of quality assurance.
  - Trust and Credibility: Increases trust and credibility in the AI-driven grading system by incorporating human oversight and expertise.

### Cons

- Resource Requirements:
  - Time and Effort: Involving expert graders requires additional time and effort, potentially increasing the overall grading process duration.
  - Human Resources: Requires the availability of qualified expert graders to review and provide feedback on AI-graded exams.
- Complexity:
  - Integration Effort: Integrating expert feedback into the AI system adds complexity to the workflow and requires careful design and implementation.
  - Coordination Overhead: Managing the coordination between AI grading and expert review can add to the system's operational complexity.
- Cost Implications:
  - Additional Costs: Involving expert graders may incur additional costs related to human resources and compensation.
  - Infrastructure: May require additional infrastructure to support the expert review process and feedback integration.
