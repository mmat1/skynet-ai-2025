# AI Case Study Grader Description

The AI Case Study Grader solution creates a comprehensive and efficient process for grading case study submissions using AI, with expert review and feedback integrated into the workflow.

## Candidate Submission:

- The candidate submits their architecture solution through the candidate UI.
- The submission is stored in the Submission Ungraded Database.

## Retrieval and Chunking:

- The submitted data is retrieved from the ungraded database.
- The data is chunked to reduce the amount of data and improve processing efficiency.

## Embedding and Storage:

- The chunked data is embedded and stored in a vector database for efficient searching and comparison.

## Criteria Retrieval:

- The detailed evaluation criteria for the case study in the form of a rubric is retrieved from the Case Study and Criteria Database.

## AI Processing:

- A a prompt orchestration layer will handle user queries and generate prompts for the LLM. The LLM will process the prompts and generate responses.
- The AI processes the candidate's submission by comparing it against the evaluation criteria in the form of a rubric and evaluates how well the submission meets the criteria and provides a detailed analysis.

## Expert Review:

- If the AI's evaluation does not meet a certain accuracy threshold set in the evaluation criteria, the submission is sent for expert review.
- The expert reviews the AI's analysis and provides additional feedback if necessary.

## Final Grading and Notification:

- The final graded submission is stored in the Architecture Grade and Feedback Database.
- Notifications are sent to the candidate regarding their results through the Candidate Architecture Notification Service, including summaries of the feedback data highlighting areas for improvement and providing insights into the overall performance of the candidate.
- Test results are also stored in the Certification Database and can be accessed through the Candidate Viewer UI.
