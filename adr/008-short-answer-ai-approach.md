---
title: Leverage RAG AI for short answer grading
authors:
  - Jag Atwal
date_created: 02/18/2025
last_updated: 02/18/2025
---

##  Leverage RAG AI for short answer grading

## Status

- Proposed: 02/18/2025
- Accepted: 02/18/2025

## Participants

- A list of participants that contributed to the decision should be provided. Example;
  - Brandon Moriarty
  - Chris Acton
  - Megin Mathew
  - Jagreet Atwal
  - Ryan Hertzog

## Context

- The Short answers are manually graded.
- With the growth of the platform and users, the number of experts needed to grade the answers is not sustainable.

## Decision

- The RAG AI approach will be used to grade the short answers.
- The Vector DB will be used to store the answers as vectors along with the additional metadata.
  - Metadata will include the question number, raw answer, version, day added etc.
- The Candidate answer will be sent to LLM to get a summarized view to the answer.
- The summarized answer will be turned into embeddings and then searched in the Vector DB for similarity.
- Vector DB will return the closest answer 3 answers and the similarity score.
- If the similarity score is above a certain threshold, the answer will be marked as valid.
- If the similarity score is below a certain threshold, the answer will be marked as not-valid.
- The 3 closest answers will be used as a context into LLM, and the summarized answer will be used to ask the LLM for matching grade.
- LLM to provide the grade based on the summarized answer.
- LLM to provide areas of improvement for the summarized answer.
- The grade and areas of improvement will be stored in AI Graded Candidate Database.
- Review Service will be used to review the AI responses and augment the feedback from any expert review.
- Any feedback from the expert review that conflicts with the AI review will be saved into AI response feedback database.
- The AI response feedback database will be used to improve the future AI responses.

### Alternatives

- **Alternative 1**
  - Instead of the Vector DB, the answers can be stored in a traditional database and then sent to LLM for grading.
    - Large number of tokens needed for LLM processing.
      - Which will be more expensive.
    - The Vector DB will be more efficient for searching for similar answers.

## Consequences

- Creation of a new Vector DB to store the answers.
- Creation of a new AI Graded Candidate Database to store the grades and areas of improvement.
- Creation of a new AI response feedback database to store the feedback from the expert review.
- The AI will be able to grade the short answers.
- The AI will be able to provide areas of improvement for the short answers.
