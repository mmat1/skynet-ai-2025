# AI Admin Case Studies feedback

This diagram details the container-level architecture for handling feedback from experts on the case studies.  The Designated Expert uses the feedback to update the case studies.

1. **Chunk**: Breaks down data into manageable chunks for processing by Prompt Orchestrator and LLM.
2. **Prompt Orchestrator**: It organizes and manages prompts for the LLM. Takes the compressed case studies and asks for LLM to summarize the content.
3. **LLM**: The Large Language Model processes the prompts and generates outputs.
4. **Summary**: The output from the LLM is summarized.
5. **Case Study Feedback Database**: Stores feedback related to case studies.
6. **Compression**: Compresses data before storing it in the Case Study Feedback Database.
7. **Pull Feedback**: Retrieves feedback from the Case Study Feedback Database for further processing or analysis.
8. **Case Study and Criteria Database**: Stores case studies along with their criteria.
9. **Case Study Maintenance Service**: Manages updates and maintenance of case studies, interacting with both databases (Case Study Feedback Database and Case Study and Criteria Database).
10. **Admin UI (User Interface)**: Allows administrators to interact with the system.
11. **Designated Experts**: Individuals who create case studies and collect feedback from Experts.
12. **Experts**: Individuals who provide feedback on case studies.
