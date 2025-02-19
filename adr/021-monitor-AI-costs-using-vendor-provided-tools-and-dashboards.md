---
title: Monitor AI costs using tools and dashboards provided by the AI service provider/platform
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

- Our AI grading system utilizes various AI services provided by external vendors.
- To ensure cost efficiency and manage our budget effectively, we need to monitor the costs associated with these AI services.
- Vendors often provide dedicated dashboards for tracking usage and costs.
- We need to decide whether to use these vendor-provided dashboards or integrate cost monitoring into our existing system.

## Decision

- We have decided to monitor AI costs using a separate dashboard provided by the vendor supplying the AI service.
- This approach leverages the vendor's specialized tools for tracking usage and costs, ensuring accurate and up-to-date information.

## Consequences

### Pros

- Accuracy:
  - Specialized Tools: Vendor-provided dashboards are designed specifically for tracking usage and costs, ensuring accurate and detailed information.
  - Real-Time Data: Provides real-time data on AI service usage and costs, enabling timely and informed decision-making.
- Efficiency:
  - No Additional Development: Avoids the need for additional development effort to integrate cost monitoring into our existing system.
  - Immediate Availability: Vendor dashboards are readily available, allowing us to start monitoring costs immediately without delay.
- Comprehensive Insights:
  - Detailed Metrics: Offers detailed metrics and breakdowns of usage and costs, providing comprehensive insights into AI service expenditures.
  - Customizable Reports: Many vendor dashboards offer customizable reports and alerts, helping us tailor the information to our specific needs.
- Resource Management:
  - Optimized Resource Use: Frees up internal resources to focus on other critical tasks, as cost monitoring is handled by the vendor's tools.
  - Scalability: Vendor dashboards are designed to scale with usage, ensuring they can handle increasing data volumes as our system grows.
- Vendor Support:
  - Dedicated Support: Access to vendor support for any issues or questions related to cost monitoring, ensuring reliable and efficient use of the dashboard.
  - Regular Updates: Vendors regularly update their dashboards to include new features and improvements, ensuring we benefit from the latest advancements.

### Cons

- Dependency on Vendor:
  - Vendor Lock-In: Relying on vendor-provided dashboards may increase dependency on the vendor, potentially limiting flexibility.
  - Data Integration: Integrating data from vendor dashboards with our internal systems may require additional effort.
- Limited Customization:
  - Customization Constraints: Vendor dashboards may have limited customization options compared to an internally developed solution.
  - Feature Limitations: May lack specific features or integrations that are tailored to our unique requirements.
- Access Management:
  - User Access: Managing user access to vendor dashboards may require additional administrative effort.
  - Data Security: Ensuring data security and privacy when using external dashboards is crucial and may require additional safeguards.
