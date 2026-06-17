# Newsletter Engagement Analytics Dashboard

This project analyzes newsletter engagement behavior to understand how readers interact with editorial content across different newsletters, audience segments, and headline variants.

It is designed to simulate real-world analytics used in media platforms to improve engagement, retention, and content strategy.

---

## Objective

The goal is to answer practical questions such as:

- Which newsletters drive the highest engagement?
- How do readers behave across regions and devices?
- Which headline variants improve click-through rates?
- Where do subscribers drop off in the engagement funnel?
- How does engagement change over time for new subscribers?

---

## Dataset

The dataset simulates newsletter activity data with the following fields:

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

Synthetic data can be generated using SQL scripts.

---

## Data Model

Star schema design:

- Fact table: newsletter_engagement

- Dimension tables:
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

## Use Cases

- Track newsletter performance
- Compare A/B headline results
- Analyze user engagement trends
- Identify drop-off points in the funnel
- Segment performance by device and region

---

## Engagement Funnel

- Emails sent  
- Opens  
- Clicks  
- Unsubscribes  

---

## Key Questions

- Which newsletter performs best?
- Which headline variant drives more clicks?
- How does engagement differ by device?
- Which region has the highest engagement?
- Where do users drop off most?
