# AI Admin Expert Refinement of Aptitude Test

This diagram details the container-level architecture for handling AI grading errors and updating the Aptitude Test database.

1. **Designated Expert**: The process starts with input from a designated expert.
2. **Admin UI**: The expert interacts with the Admin UI, which serves as the interface for managing the system.
3. **Aptitude Test Maintenance Service**: This service maintains the aptitude tests and interacts with the Aptitude Test Database.
4. **Aptitude Test Database**: Stores data related to aptitude tests.
5. **Aptitude Test Analysis Service**: This service provides analysis of Aptitude Tests.
6. **AI Service for Short & Multiple Answer Analysis**: Analyzes short answers and multiple-choice responses, feeding back into Aptitude Test Analysis Service or pulling feedback from AI Response Feedback Database.
7. **Summary**: Summarized output from LLM on why the candidate answers were wrong for the question and answer provided as the context.
8. **LLM (Large Language Model)**: Processes information and provides language-based analysis or responses.
9. **Prompt Orchestrator**: Manages prompts for LLM. Provides to LLM the following context: Aptitude Test Question & Answer and the candidate's answer; and then asks LLM to provide feedback on what could be changed in the question and answer to help candidates' answers.
10. **Chunk Data**: Breaks down data into manageable chunks for processing by Prompt Orchestrator and LLM.
11. **AI Response Feedback Database**: Stores feedback pulled by Chunk Data to improve AI responses.
12. **Compression**: Compresses data before sending it to AI Service for Short & Multiple Answer Analysis.