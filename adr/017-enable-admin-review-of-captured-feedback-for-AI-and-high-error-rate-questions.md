---
title: Admin review of captured feedback on overridden AI Grades and high incorrect response rates
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

- Our AI grading system evaluates candidate responses and assigns grades based on predefined criteria.
- Expert graders have the ability to review and override AI-assigned grades, providing valuable feedback.
- Additionally, some questions may have a high incorrect response rate (e.g., 95% of candidates answered incorrectly).
- To ensure continuous improvement and maintain the quality of our grading system, we need a process to review these cases.
- The Admin UI, where questions are created and modified, will serve as the moderation interface for managing inputs used by the AI grading system, including questions, grading criteria, acceptable answers, and expert feedback.

## Decision

- We have decided to review captured feedback on questions with AI grades that were overridden by grading experts and to review questions where 95% of candidates were incorrect in their answers.
- This review process will be integrated into the Admin UI, allowing for effective moderation and management of the inputs used by the AI grading system.

## Consequences

### Pros

- Continuous Improvement:
  - Feedback Utilization: Reviewing expert feedback on overridden AI grades allows us to identify and address any discrepancies, leading to continuous improvement of the AI grading system.
  - Error Correction: Helps in identifying and correcting errors in the AI's grading logic, improving overall accuracy and reliability.
- Enhanced Accuracy:
  - High Incorrect Response Rates: Reviewing questions with high incorrect response rates helps identify potential issues with the question design, grading criteria, or acceptable answers, leading to more accurate evaluations.
  - Refinement: Enables refinement of questions, grading criteria, and acceptable answers based on real-world performance data.
- Quality Assurance:
  - Expert Oversight: Incorporating expert feedback ensures that the grading system maintains high standards of quality and fairness.
  - Consistency: Regular reviews help maintain consistency in grading and evaluation, ensuring that all candidates are assessed fairly.
- Improved User Experience:
  - Actionable Insights: Provides actionable insights for educators and administrators to improve question design and grading criteria.
  - Transparency: Increases transparency in the grading process, building trust among candidates and stakeholders.
- Efficient Moderation:
  - Integrated Admin UI: Centralizes the review process within the Admin UI, streamlining the workflow and making it easier for administrators to manage and update the system.
  - Comprehensive Management: Allows for comprehensive management of questions, grading criteria, acceptable answers, and expert feedback in one place.

### Cons

- Resource Requirements:
  - Time and Effort: Reviewing captured feedback and high incorrect response rates requires additional time and effort from administrators and expert graders.
  - Human Resources: Requires the availability of qualified experts to conduct the reviews and provide feedback.
- Complexity:
  - Integration Effort: Integrating the review process into the Admin UI adds complexity to the system and requires careful design and implementation.
  - Coordination Overhead: Managing the coordination between AI grading, expert review, and feedback integration can add to the system's operational complexity.
- Cost Implications:
  - Additional Costs: Involving expert graders and conducting regular reviews may incur additional costs related to human resources and infrastructure.
  - Infrastructure: May require additional infrastructure to support the review process and feedback integration.
