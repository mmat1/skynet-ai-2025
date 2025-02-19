# Admin Bad Question Review Description

If 95% of all candidates miss the same question, analysis should be done to modify the question or remove it.

## 1. Designated Expert: 

Represents a person responsible for overseeing or managing the process.

## 2. Aptitude Test Grade Database: 

Stores the aptitude test grades per question.

## 3. Aptitude Test Analysis Service:

Used to analyze aptitude certification test questions 
based on reports and analysis of question correctness 
percentages. Accessed by designated experts to 
periodically check the validity of the aptitude certification 
tests

## 4. Candidate Exam Data Vectorization

-**Retrieval and Chunking**:

- The candidate exam data is retrieved from the database.
- The data is chunked to reduce the amount of data and improve processing efficiency.

-**Embedding and Storage**:

- The chunked data is embedded and stored in a vector database for efficient searching and comparison.

## 5. Aptitude Test Answer Vectorization

-**Retrieval and Chunking**:

- The answers are retrieved from the service.
- The data is chunked to reduce the amount of data and improve processing efficiency.

-**Embedding and Storage**:

- The chunked data is embedded and stored in a vector database for efficient searching and comparison.


## 6. AI Short-Answer/Auto Critique Error Review: 

Reviews short answers and critiques errors automatically.

-**Data Retrieval**: The top N incorrectly answered questions are retrieved from the Aptitude Test Analysis Service.

- **Prompt Orchestrator**: Manages and organizes prompts for further processing.

- **LLM (Large Language Model)**: A large language model used to analyze why the questions were answered incorrectly.

- **Inputs**: Equation & logic + assessment.

- **Outputs**: Reviewed answer analysis is sent back to Aptitude Test Analysis Service.