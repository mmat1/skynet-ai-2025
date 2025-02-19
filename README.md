# Skynet AI | O'Reilly Kata: Architecture & AI (Winter 2025)

<div align="center" style="text-align: center;">
   <img src="adr/images/SkynetAI-kata.png" alt="O'Reilly Architecture Kata: Winter 2025 - Architecture & AI" width="400" height="400" />
</div>

---

## **Table of Contents**

- [Overview](#overview)
  - [About the project](#about-the-project)
  - [Team Members](#team-members)
  - [Deliverables](#deliverables)
  - [Judges' Criteria](#judges-criteria)
- [About Certifiable, Inc](#about-certifiable-inc)
  - [Certification Process](#certification-process)
- [Requirements](#requirements)
  - [Functional Requirements](#functional-requirements)
  - [Non-Functional Requirements](#non-functional-requirements)
  - [Assumptions and Constraints](#assumptions-and-constraints)
  - [AI Opportunities](#ai-opportunities)
- [Architecture and Design](#architecture-and-design)
  - [Current Architecture](#current-architecture)
  - [Future Architecture](#future-architecture)
  - [Architecture Decision Records](#architecture-decision-records)

## Overview

### About the project

The purpose of this GitHub repository is to explore and identify opportunities for the use of Generative AI within Certifiable Inc.'s existing certification system. The goal is to redesign the architecture to support AI-driven enhancements that can manage the increased demand for software architecture certifications.

### Team Members

- Brandon Moriarty
- Chris Acton
- Jagreet Atwal
- Megin Mathew
- Ryan Hertzog

### Deliverables

The following deliverables will be provided:

- **Overview**: A narrative describing how AI is used in the certification system.
- **Diagrams**: Comprehensive views for each use of AI.
- **ADRs**: Architectural Decision Records for AI implementations, including trade-off analysis.
- **Implementation Details**: Pertinent implementation details (optional).
- **Video**: A five-minute video describing the team's approach (for semi-final teams).

### Judges' Criteria

The solutions will be evaluated based on:

- Innovative use of Generative AI.
- Suitability of the solution given the constraints.
- Appropriate levels of detail.
- Use of AI architecture patterns.
- Avoidance of AI architecture anti-patterns.
- Validation and verification of AI results.

## About Certifiable, Inc

Certifiable Inc. is a leading company in software architecture certification, based in the United States. The company provides accredited certification to qualified software architects through its flagship system, SoftArchCert. With the recent acceptance of software architecture certification in Europe, the U.K., and Asia, Certifiable Inc. is anticipating a significant increase in certification requests. This repository aims to explore opportunities to introduce AI to their current certification process to handle the expected growth efficiently.

### Certification Process

Certifiable Inc.'s certification process involves two main tests:

1. **Aptitude Test**: This test includes multiple-choice and short-answer questions. Multiple-choice questions are auto-graded, while short-answer questions are graded manually by expert software architects.
2. **Architecture Submission**: Candidates must create an architecture for a randomly assigned case study. The submissions are reviewed and graded by expert software architects.

## Requirements

### Functional Requirements

### Non-Functional Requirements

### Assumptions and Constraints

Certifiable Inc. faces several challenges due to the anticipated increase in certification requests:

- Manual grading of short-answer questions and architecture submissions is time-consuming.
- Currently, Certifiable, Inc. has on average 200 candidates per week seeking certification across the U.S.
- Candidate certifications are expected to grow 5-10X based on oversees expansion as well as the anticipated 21% growth over the next 4 years.
- The current system may not be able to handle the increased volume of certification requests.
- Ensuring the accuracy and reliability of the certification process is critical.

### AI Opportunities

The architecture team will explore the following AI opportunities:

- **Automated Grading**: Implementing AI to grade short-answer questions and architecture submissions.
- **AI-Driven Feedback**: Using AI to provide detailed feedback to candidates.
- **Scalability**: Redesigning the system architecture to support AI-driven enhancements and handle increased demand.

## Architecture and Design

### Current Architecture

#### Admin

<div align="center" style="text-align: center;">
   <img src="adr/images/Existing Administrative Architecture.drawio.png" alt="Admin Application"/>
</div>

#### Certification

##### Case Study

<div align="center" style="text-align: center;">
   <img src="adr/images/Existing Certification Testing Architecture - Architecture Solution.drawio.png" alt="Existing Certification Testing Diagram"/>
</div>

##### Aptitude

<div align="center" style="text-align: center;">
   <img src="adr/images/Existing Certification Testing Architecture-Test1.drawio.png" alt="Existing Certification Testing Diagram"/>
</div>

### Future Architecture

### Architecture Decision Records

An Architecture Decision Record (ADR) is a document that captures an important architectural decision made along with its context and consequences. It helps teams keep track of the architectural history and rationale behind decisions, ensuring transparency and facilitating future maintenance and evolution of the system. The following template will be used for all ADRs; [ADR template](adr/000-adr-template.md)

- [001 - Create an index per question and version for short answer Vector DB](adr/001-create-index-per-question-and-version-for-short-answer-vector-db.md)
- [002 - Use Vector DB to store raw content and embeddings](adr/002-use-vector-database-to-store-raw-content-and-embeddings.md)
- [003 - Store candidate aptitude test submissions by question](adr/003-store-candidate-aptitude-test-submissions-by-question.md)
- [004 - Data will be chunked before storing](adr/004-data-will-be-chunked-before-storing.md)
- [005 - Apply embeddings model before storing to Vector DB](adr/005-apply-embeddings-model-before-storing-to-vector-database.md)
- [006 - Version Vector DB indexes and stored data](adr/006-version-vector-database-indexes-and-stored-data.md)
- [007 - Apply filtering to Vector DB results before sending to LLM](adr/007-apply-filtering-to-vector-db-results-before-sending-to-LLM.md)
- [008 - Validate prompts before sending information to LLM for processing](adr/008-validate-prompts-before-sending-information-to-LLM-for-processing.md)
- [009 - Implement prompt orchestrator to manage prompts](adr/009-implement-prompt-orchestrator-to-manage-prompts.md)
- [010 - LLM will evaluate and grade one question at a time](adr/010-LLM-will-evaluate-and-grade-one-question-at-a-time.md)
- [011 - Use prompt compression before LLM processing](adr/011-use-prompt-compression-before-LLM-processing.md)
- [012 - Storing AI graded exams as a single ready to review record](adr/012-storing-AI-graded-exams-as-a-single-ready-to-review-record.md)
- [013 - Allow expert graders to provide feedback for AI graded-exams](adr/013-allow-expert-graders-to-provide-feedback-for-AI-graded-exams.md)
- [014 - Store expert grader AI response feedback for tuning](adr/014-store-expert-grader-AI-response-feedback-for-tuning.md)
- [015 - Use grading criteria and rubric to evaluate and grade case study submissions](adr/015-use-grading-criteria-and-rubric-to-evaluate-and-grade-case-study-submissions.md)
- [016 - Dynamically create embeddings for case study submissions](adr/016-dynamically-create-embeddings-for-case-study-submissions.md)
- [017 - Enable admin review of captured feedback for AI and high error rate questions](adr/017-enable-admin-review-of-captured-feedback-for-AI-and-high-error-rate-questions.md)
- [018 - Gather and summarize feedback from certifiable experts for new exam questions](adr/018-gather-and-summarize-feedback-from-certifiable-experts-for-new-exam-questions.md)
- [019 - Use existing databases to measure observability metrics](adr/019-use-existing-databases-to-measure-observability-metrics.md)
- [020 - Build dashboard for SLO/SLA for AI services](adr/020-build-dashboard-for-SLO-SLA-for-AI-services.md)
- [021 - Monitor AI costs using vendor provided tools and dashboards](adr/021-monitor-AI-costs-using-vendor-provided-tools-and-dashboards.md)
