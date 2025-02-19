---
title: Use grading criteria and rubric, defined by Certifiable Inc experts, to evaluate candidate Case Study submissions
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

- As a recognized leader in certification, maintaining the accuracy of tests, case studies, and grading is crucial. Inaccurate grading can prevent candidates from obtaining or retaining employment, significantly impacting their careers. Furthermore, inaccurate or misleading certification exams and case studies can damage the company's credibility in the marketplace.
- Therefore, ensuring the accuracy of the certification process is essential for the company's success.
- Our AI grading system evaluates various types of exam questions, including multiple choice, short answer, and case studies.
- To ensure accurate and consistent evaluation of candidate case study architecture submissions, we need a robust grading framework.
- Designated experts have created detailed grading criteria through an Admin UI, which includes managing multiple choice, short answer, and case studies along with grading criteria and potential acceptable answers.
- Additionally, a rubric will be part of the grading criteria, and the AI should assign a value for each grading criterion based on this rubric to maintain consistency across all exams.

## Decision

- We have decided to use the case study grading criteria provided by designated experts, incorporating a rubric to evaluate candidate case study architecture submissions. The AI will assign a value for each grading criterion based on the rubric, ensuring consistent and accurate evaluation.

## Consequences

### Pros

- Expert Validation:
  - High-Quality Standards: Grading criteria and rubric created by designated experts ensure evaluations are based on high-quality standards and best practices.
  - Consistency: Provides a consistent framework for evaluating all candidate submissions, reducing variability in grading.
- Accuracy:
  - Detailed Criteria and Rubric: Detailed grading criteria and rubric allow for precise and accurate evaluation of complex case study submissions.
  - Comprehensive Assessment: Ensures that all relevant aspects of the candidate's architecture submission are thoroughly assessed.
- Enhanced Feedback:
  - Specific Guidance: Enables the provision of specific and actionable feedback to candidates, helping them understand their strengths and areas for improvement.
  - Clear Expectations: Clearly communicates the expectations and standards to candidates, guiding them in their preparation and submission.
- Efficiency:
  - Streamlined Process: Using predefined grading criteria and rubric streamlines the evaluation process, making it more efficient and reducing the time required for grading.
  - Automated Evaluation: Facilitates the automation of the grading process, leveraging AI to apply the criteria and rubric consistently.
- Continuous Improvement:
  - Feedback Loop: Allows for continuous improvement of the grading criteria and rubric based on feedback from expert graders and candidate performance.
  - Adaptive Learning: The system can adapt and refine the grading criteria and rubric over time, ensuring they remain relevant and effective.
- Consistency Across Exams:
  - Uniform Application: Ensures that the grading criteria and rubric are applied uniformly across all exams, maintaining consistency and fairness in grading.
  - Standardized Evaluation: Standardizes the evaluation process, ensuring that all candidates are assessed based on the same criteria and rubric.

### Cons

- Resource Requirements:
  - Initial Setup: Creating and maintaining detailed grading criteria and rubric requires significant input and effort from designated experts.
  - Ongoing Maintenance: Regular updates and adjustments to the grading criteria and rubric may be needed to keep them aligned with evolving standards and practices.
- Complexity:
  - Integration Effort: Integrating the grading criteria and rubric into the AI-driven grading system adds complexity to the workflow and requires careful design and implementation.
  - Coordination Overhead: Managing the coordination between expert input, AI evaluation, and feedback integration can add to the system's operational complexity.
- Potential Rigidity:
  - Fixed Criteria: Relying on predefined grading criteria and rubric may limit flexibility in evaluating unique or innovative submissions that do not fit neatly into the established framework.
  - Adaptation Challenges: Adapting the criteria and rubric to accommodate new types of case studies or evolving industry standards may require significant effort.
