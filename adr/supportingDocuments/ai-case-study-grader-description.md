# AI Case Study Grader Description

The AI Case Study Grader solution creates a comprehensive and efficient process for grading case study submissions using AI, with expert review and feedback integrated into the workflow.

## Candidate Submission:

- The candidate submits their architecture solution through the candidate UI.
- The submission is stored in the "Architecture Submission Ungraded Database".

## Retrieval and Chunking:

- The submitted data is retrieved from the ungraded database.
- The data is chunked to reduce the amount of data and improve processing efficiency.

## Embedding and Storage:

- The chunked data is embedded and stored in a vector database for efficient searching and comparison.
- **Data Sources**: Collect data from various sources such as case study responses, expert reviews, and historical data.
- **Storage**: Store the data in a structured format in a database (e.g., Azure SQL Database).

## Criteria Retrieval:

- The detailed evaluation criteria for the case study are retrieved from the "Case Study Database".

## AI Processing:

- The AI processes the candidate's submission by comparing it against the evaluation criteria.
- The AI evaluates how well the submission meets each criterion and provides a detailed analysis.
- **Data Pipeline**: Use Azure Data Factory or Azure Synapse Analytics to create a data pipeline that processes and transforms the data.
- **Indexing**: Use Azure Cognitive Search to index the data and create embeddings for efficient retrieval.
- **Embeddings Generation**: Use Azure OpenAI to generate embeddings for the indexed data.
- **Vector Database**: Store the embeddings in a vector database (e.g., Azure Cosmos DB).

## Expert Review:

- If the AI's evaluation does not meet a certain threshold, the submission is sent for expert review.
- The expert reviews the AI's analysis and provides additional feedback if necessary.

## Final Grading and Notification:

- The final graded submission is stored in the "Final Graded Exam Database".
- Notifications are sent to the candidate regarding their results.
- If the candidate passes, a certificate is generated and stored in the "Certification Database".

## RAG Model Implementation:

- **Prompt Orchestration**: Implement a prompt orchestration layer to handle user queries and generate prompts for the LLM.
- **LLM Integration**: Integrate with an LLM (e.g., OpenAI GPT-3) to process the prompts and generate responses.

## Grading and Feedback:

- **AI Grading**: Use the LLM to grade case study responses based on an answer key and provide feedback.
- **Expert Review**: Allow experts to review AI-graded results and provide additional feedback.

## Observability and Monitoring:

- **Observability Features**: Implement observability features to monitor AI accuracy, bias, and performance.
- **Feedback Loop**: Continuously update the model based on expert feedback and new data.

## Notification and Reporting:

- **Candidate Notification**: Notify candidates with relevant feedback through appropriate channels (e.g., email, LMS).
- **Reporting**: Generate reports summarizing the feedback data, highlighting common areas of improvement, and providing insights into the overall performance of candidates.

## Components:

- **Data Sources**: Test responses, case studies, expert reviews.
- **Storage**: Azure SQL Database.
- **Data Pipeline**: Azure Data Factory or Azure Synapse Analytics.
- **Indexing**: Azure Cognitive Search.
- **Embeddings Generation**: Azure OpenAI.
- **Vector Database**: Azure Cosmos DB.
- **Prompt Orchestration**: Handles user queries and generates prompts.
- **LLM Integration**: OpenAI GPT-3 for processing prompts and generating responses.
- **Observability Features**: Monitor AI accuracy, bias, and performance.
- **Notification and Reporting**: Communicate feedback to candidates and generate performance reports.
