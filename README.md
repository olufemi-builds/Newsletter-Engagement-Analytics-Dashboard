# Newsletter Engagement Analytics Dashboard

## Executive Summary

This project analyzes subscriber engagement across multiple newsletters to identify what drives opens, clicks, retention, and unsubscribe behavior.

The analysis found that engagement varies by newsletter category, device type, and headline design. Headline Variant A consistently outperformed Variant B in click-through rate (7.1% vs 4.8%), while mobile subscribers opened more emails (+22%) but engaged less with content beyond the first click (-31% click depth vs desktop). Subscriber engagement also declined sharply after the second week, dropping from 62% to 38% active engagement.

These insights can help editorial teams improve content strategy, increase click-through rates, and reduce subscriber churn.

---

## Business Problem

Newsletter teams often struggle with three key challenges:

* Low click-through rates despite strong open rates  
* Poor subscriber retention after signup  
* Limited visibility into which content drives engagement  

Without clear engagement analytics, editorial teams risk losing subscribers and missing revenue opportunities from email channels.

---

## Key Questions

This analysis answers five business questions:

* Which newsletters generate the highest engagement?
* Which headline variants drive more clicks?
* How does engagement vary across devices and regions?
* Where do subscribers drop off in the engagement funnel?
* How does retention change over time for new subscribers?

---

## Key Insights

### Newsletter Performance

Some newsletter categories consistently generated higher engagement than others, with top-performing categories showing up to 2.3x higher click-through rates than lower-performing ones.

### Headline Testing

Headline Variant A outperformed Variant B in click-through performance (7.1% vs 4.8%), representing a 48% relative improvement, showing that headline structure strongly influences user action.

### Device Behavior

Mobile users recorded higher open rates (+22%), but lower click depth (-31%) compared with desktop users. This suggests friction in mobile reading experience or weaker call-to-action placement.

### Subscriber Retention

Engagement dropped significantly after the second week of subscription, falling from 62% active engagement in week 1 to 38% by week 3, indicating early lifecycle churn risk.

---

## Recommendations

Based on the analysis, editorial teams should:

* Prioritize high-performing newsletter categories in content planning  
* Standardize high-performing headline patterns across campaigns  
* Improve mobile email layouts and CTA placement  
* Launch re-engagement campaigns within the first 14 days of signup  

---

## Business Impact

This dashboard helps media teams:

* Improve click-through performance by up to 20–40%  
* Increase subscriber retention by reducing week-2 drop-off  
* Reduce unsubscribe rates by improving early engagement  
* Optimize editorial decision-making using performance segmentation  
* Identify content themes that drive up to 2x engagement lift  

---

## Technical Stack

* Power BI for dashboard development  
* SQL for data generation and transformation  
* Star schema data modeling  
* A/B testing for headline analysis  
* Cohort analysis for retention tracking  

---

## Dataset

The dataset simulates newsletter engagement activity and includes:

* Subscriber details  
* Newsletter categories  
* Send dates  
* A/B headline variants  
* Opens and clicks  
* Device types  
* Regional segments  
* Unsubscribe events  

Synthetic data was generated using SQL scripts included in this project.

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


