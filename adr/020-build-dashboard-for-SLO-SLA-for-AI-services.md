---
title: Build a dashboard to display SLA and SLO for AI services
authors:
  - Ryan Hertzog
date_created: 02/19/2025
last_updated: 02/19/2025
---

## Status

- Proposed: 02/19/2025
- Accepted: 02/19/2025

## Participants

- Brandon Moriarty
- Chris Acton
- Megin Mathew
- Jagreet Atwal
- Ryan Hertzog

## Context

- Our AI grading system involves multiple AI services that contribute to the candidate certification process.
- To ensure the system meets performance and reliability standards, we need to monitor Service Level Agreements (SLA) and Service Level Objectives (SLO) for these AI services.
- Additionally, we aim to measure AI accuracy, bias, reduction in overall time of the candidate certification process, and reduction in labor.
- This dashboard will be associated with the observability metrics previously mentioned (refer to: [ADR - 019](/adr/019-use-existing-databases-to-measure-observability-metrics.md)) and will provide a comprehensive view of the system's performance.

## Decision

- We have decided to build a dashboard to display SLA and SLO for the different AI services added.
- The dashboard will be used to manually evaluate and review AI accuracy, bias, reduction in overall time of the candidate certification process, and reduction in labor.

## Consequences

### Pros

- Enhanced Monitoring:
  - Real-Time Insights: Provides real-time insights into the performance and reliability of AI services, enabling proactive monitoring and management.
  - Comprehensive View: Offers a comprehensive view of SLA and SLO metrics, helping to ensure that the system meets performance and reliability standards.
- Improved Accuracy and Bias Detection:
  - Accuracy Measurement: Allows for manual measurement of AI accuracy, helping to identify and address any discrepancies or errors.
  - Bias Detection: Facilitates the detection and mitigation of bias in AI services, ensuring fairness and equity in the grading process.
- Efficiency Gains:
  - Time Reduction: Measures the reduction in overall time of the candidate certification process, highlighting efficiency gains and areas for improvement.
  - Labor Reduction: Tracks the reduction in labor required for the certification process, demonstrating the impact of AI automation.
- Data-Driven Decision Making:
  - Actionable Insights: Provides actionable insights based on SLA and SLO metrics, enabling data-driven decision making and continuous improvement.
  - Performance Optimization: Helps identify performance bottlenecks and areas for optimization, leading to a more efficient and effective system.
- Transparency and Accountability:
  - Clear Metrics: Displays clear and transparent metrics for SLA and SLO, building trust and accountability among stakeholders.
  - Stakeholder Communication: Facilitates communication with stakeholders by providing a visual representation of system performance and reliability.

### Cons

- Resource Requirements:
  - Development Effort: Building and maintaining the dashboard requires significant development effort and expertise.
  - Ongoing Maintenance: Requires ongoing maintenance to ensure the dashboard remains accurate and up-to-date.
- Complexity:
  - Integration Effort: Integrating the dashboard with existing systems and data sources adds complexity to the architecture.
  - Data Management: Managing and visualizing large volumes of data from multiple AI services can be challenging.
- Cost Implications:
  - Additional Costs: Developing and maintaining the dashboard may incur additional costs related to development, infrastructure, and maintenance.
  - Infrastructure: May require additional infrastructure to support real-time data collection, processing, and visualization.
