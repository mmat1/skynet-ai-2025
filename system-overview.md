# System Overview

Please refer to the [business case and requirements](requirements.md) for reason and need for this system.

## Executive Summary

1. **Problem and Actors**:
   - We identified four key actors in our solution: **Candidates**, **Expert Software Architect** , **Designated Expert Software Architect** and **Administrator**.
   - Our goal is to ensure that the current Certifiable Inc software can handle the increased demand for software architecture certifications as they expand to U.K., Europe and Asia, by leveraging AI to streamline the manual process they currently have in place to grade the exams.

2. **Architecture Characteristics**:

   We prioritized **Performance** and **Accuracy** as our top concern.

    #### Performance

    1. **Efficiency and Speed:** AI grading systems can process and evaluate submissions much faster than human graders. This efficiency is crucial for handling the anticipated increase in certification requests, ensuring that results are delivered promptly.
    2. **Scalability:** AI systems can easily scale to handle large volumes of submissions without compromising on speed or quality. This scalability is essential for managing the expected 5-10X increase in demand.
    3. **Reduced Workload:** By automating the grading process, AI reduces the workload on human experts, allowing them to focus on more complex and nuanced tasks that require human judgment.

    #### Accuracy

    1. **Consistency:** AI grading systems follow predefined rules and standards, ensuring consistent and objective evaluations. This consistency helps maintain high standards across all submissions.
    2. **Error Reduction:** AI systems are less prone to fatigue and human error, which can lead to more accurate grading.
    3. **Continuous Improvement:** AI systems can learn and improve over time by incorporating feedback from expert reviewers, leading to increasingly accurate evaluations.

    Implicit Characteristics
    
    #### Security

    1. **Data Protection:** Ensuring that all data, including candidate submissions and grading results, are securely stored and transmitted and no PII information is fed to the AI services.
    2. **Access Control:** Implementing strict access controls to ensure that only authorized personnel can access sensitive information.
    3. **Compliance:** Adhering to relevant data protection regulations and standards for each country to maintain the integrity and confidentiality of the data.

    #### Feasibility

    1. **Technical Viability:** Assessing the technical requirements and ensuring that the AI systems can be integrated seamlessly with existing infrastructure.
    2. **Cost-Effectiveness:** Evaluating the cost implications and ensuring that the implementation of AI systems is financially viable.
    3. **Resource Availability:** Ensuring that the necessary resources, including skilled personnel and technology, are available for the successful implementation of the AI systems.

    #### Availability

    1. **System Uptime:** Ensuring that the AI grading systems are available and operational at all times to handle submissions without interruption.
    2. **Redundancy:** Implementing redundancy measures to prevent system failures and ensure continuous availability.
    3. **Support and Maintenance:** Providing ongoing support and maintenance to address any issues promptly and ensure the smooth operation of the AI systems.

3. **New AI System Components**:

- AI Short Answer Auto Grader
  - This AI Service will grade short answers based on an answer key.
- AI Case Study Auto Grader
  - This AI service will grade case studies based on criteria and rubrics.
- Case Study AI Pipeline Service
  - This AI service will provide a pipeline for case study grading and provide a rank based on the rubric.
- Exam Data AI Pipeline
  - This AI service will provide a pipeline for exam data and store the information into a Vector database for similarity search.
- AI Service for Short and Multiple Answer Analysis
  - This AI service will analyze short answers and multiple-choice responses, feeding back into the Aptitude Test Analysis Service or pulling feedback from the AI Response Feedback Database.
- Question/Answer Data Pipeline AI Service
  - This AI service will take the experts question and answer data and store it into a Vector database for similarity search.


4. **Comprehensive Diagrams**

    Icepanel : https://s.icepanel.io/7x0vWrdHnLch4R/yBIc

   ### Admin Application

<div align="center" style="text-align: center;">
   <img src="diagrams/architecture-admin-app-comprehensive-diagram.png" alt="Admin Application Comprehensive Diagram"/>
</div>

   ### Certification Application

<div align="center" style="text-align: center;">
   <img src="diagrams/architecture-certification-app-comprehensive-diagram.png" alt="Admin Application Comprehensive Diagram"/>
</div>



