---
title: LLM will process one question at a time
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

- Our RAG AI grading system for short answer questions aims to provide accurate and efficient grading and feedback to students. To achieve this, we need to determine the best approach for evaluating and grading candidate exam responses using our selected LLM. One option is to process multiple questions in a batch, while another is to process one question at a time.
- Given the need for precision, clarity, and detailed feedback, we need to decide on the most effective method for AI to process exam questions.

## Decision

- We have decided to configure the LLM to process one question at a time rather than processing multiple questions in a batch.

## Consequences

### Pros

- Improved Accuracy:
  - Focused Evaluation: Processing one question at a time allows the LLM to focus on the specific context and nuances of each question, leading to more accurate evaluations.
  - Detailed Feedback: Enables the LLM to provide more detailed and specific feedback for each question, helping students understand their performance better.
- Clarity and Consistency:
  - Clear Responses: Ensures that the LLM's responses are clear and contextually relevant to each individual question.
  - Uniform Grading: Maintains consistency in grading by applying the same evaluation criteria to each question independently.
- Error Isolation:
  - Easier Debugging: Isolating the processing of each question makes it easier to identify and address errors or issues in the evaluation process.
  - Quality Control: Allows for better quality control by reviewing and validating the LLM's output for each question separately.
- Resource Management:
  - Optimized Resource Use: Allocates computational resources more effectively by processing questions sequentially, reducing the risk of resource contention.
  - Scalability: Facilitates scalability by allowing the system to handle varying loads more efficiently, as each question is processed independently.

### Cons

- Increased Latency:
  - Longer Processing Time: Processing questions one at a time may increase the overall processing time compared to batch processing.
  - Potential Delays: May introduce delays in providing feedback, especially for exams with a large number of questions.
- Resource Utilization:
  - Higher Computational Load: Sequential processing may result in higher computational load, as each question requires separate processing.
  - Efficiency Trade-offs: May trade off some efficiency for improved accuracy and clarity.
- Complexity in Workflow:
  - Workflow Management: Managing the sequential processing workflow can add complexity to the system's architecture.
  - Coordination Overhead: Requires careful coordination to ensure that each question is processed in the correct order and within the required time frame.
