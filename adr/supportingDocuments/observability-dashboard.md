# Observability Dashboard

The Observability Dashboard helps review AI accuracy, performance, and the overall reduction in time taken to evaluate certification exams.


## Dashboard Metrics

### Overall Reduction in Evaluation Time

- **Average Turnaround Time for Aptitude Test Results:** Measures the average time taken to grade and return results for the aptitude test, which includes multiple-choice questions and short answers. This metric tracks the duration from when the candidate submits their exam to when the final grades are recorded in the database.
- **Average Turnaround Time for Case Study Results:** Measures the average time taken to grade and return results for the architecture case studies.This metric tracks the duration from when the candidate submits their architecture for the case study to when the final grades and feedback are recorded in the database.

### Accuracy
- **Percentage of Aptitude Tests Accurately Graded by AI Autograder:** Indicates the percentage of Aptitude Tests(short answers) accurately graded by the AI auto grader without requiring any corrections from the expert reviewer. 
- **Percentage of Case Studies Accurately Graded by AI Autograder:** Indicates the percentage of case study architectures accurately graded by the AI auto grader without requiring any corrections from the expert reviewer. 

### Performance
- **Average Grading Time for AI Autograder for a Short Answer:** Measures the average time taken by the AI Autograder to grade an individual short answer.
- **Average Grading Time for AI Autograder for a Case Study:** Measures the average time taken by the AI Autograder to grade a case study.


## Analytics Service Functions
- **Data Collection and Storage:** Connects to various databases to collect and store data related to aptitude tests, case studies, and feedback.
- **Data Analysis:** Analyzes the collected data to generate insights on AI accuracy, performance, and evaluation time.
- **Performance Monitoring:** Monitors key metrics such as average turnaround time, grading accuracy, and grading time for both aptitude tests and case studies.

### Connected Databases
The Analytics Service connects to the following databases:
1. **Aptitude Test Ungraded Database:** Stores ungraded aptitude test submissions.
2. **Question/Answer Vector Database:** Stores vector representations of questions and answers.
3. **AI Graded Test 1 Database:** Stores results of aptitude tests graded by the AI.
4. **Expert Graded Database:** Stores the exam grades after review by the SA experts(this is after the AI grades it).
5. **Submission Ungraded Database:** Stores ungraded case study submissions.
6. **AI Graded Architecture Database:** Stores results of architecture case studies graded by the AI.
7. **Architecture Grade and Feedback:** Stores the final grades and feedback for architecture case studies.
8. **AI Response Feedback Database:** Stores feedback on AI grading added by the expert reviewers and gives the data for the AI grades which were corrected by the experts.