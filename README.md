# Newsletter Engagement Analytics Dashboard

This project analyzes newsletter engagement behavior to understand how readers interact with editorial content across newsletters, audience segments, and headline variants.

It simulates analytics used in media platforms to improve engagement, retention, and content strategy.

---

## Problem

Newsletter teams often face:

- Low click-through rates  
- Declining retention after signup  
- Unclear headline performance  
- Weak segmentation of audience behavior  

---

## Objective

This project focuses on answering:

- Which newsletters drive the highest engagement?
- How do readers behave across regions and devices?
- Which headline variants improve click-through rates?
- Where do subscribers drop off in the engagement funnel?
- How does engagement change over time for new subscribers?

---

## Approach

A structured analytics model was built using:

- Power BI for dashboards and visualization  
- SQL for data generation and transformation  
- Star schema data modeling  
- A/B testing for headline comparison  
- Cohort analysis for retention tracking  

### Analysis focus areas

- Newsletter performance comparison  
- Regional engagement patterns  
- Device-based behavior (mobile vs desktop)  
- Headline variant testing  
- Subscriber retention trends  

---

## Dataset

The dataset simulates newsletter activity.

### Fields

- subscriber_id  
- signup_date  
- newsletter_name  
- send_date  
- headline_variant (A/B test)  
- opens  
- clicks  
- device_type  
- region  
- unsubscribed  

Synthetic data is generated using SQL scripts included in the project.

---

## Data Model

Star schema design used for analytics.

### Fact table
- newsletter_engagement  

### Dimension tables
- dim_subscriber  
- dim_newsletter  
- dim_date  

### Relationships

- subscriber_id → dim_subscriber  
- newsletter_name → dim_newsletter  
- send_date → dim_date  

---

## Key Metrics (DAX)

```DAX
Total Opens =
SUM(newsletter_engagement[opens])

Total Clicks =
SUM(newsletter_engagement[clicks])

Open Rate =
DIVIDE(
    SUM(newsletter_engagement[opens]),
    COUNTROWS(newsletter_engagement)
)

Click Rate =
DIVIDE(
    SUM(newsletter_engagement[clicks]),
    SUM(newsletter_engagement[opens])
)
Unsubscribe Rate =
DIVIDE(
    SUM(newsletter_engagement[unsubscribed]),
    COUNTROWS(newsletter_engagement)
)


---

## Key Findings

- One newsletter category consistently drives higher click-through rates  
- Mobile users show higher open rates but lower click depth  
- Headline variant A performs better than variant B  
- Engagement drops after the second week for new subscribers  

---

## Engagement Funnel

- Emails sent  
- Opens  
- Clicks  
- Unsubscribes  

---

## Use Cases

- Track newsletter performance  
- Compare A/B headline results  
- Analyze user engagement trends  
- Identify drop-off points in the funnel  
- Segment performance by device and region  

---

## Business Impact

This project helps media teams:

- Increase engagement per send  
- Improve subscriber retention  
- Optimize editorial planning  
- Identify high-performing content themes early  

---

## Key Questions Answered

- Which newsletter performs best?  
- Which headline variant drives more clicks?  
- How does engagement differ by device?  
- Which region has the highest engagement?  
- Where do users drop off most?  
