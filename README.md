# RevOps-Portfolio
RevOps Practice Projects

# AI Pipeline Health Reporter

## Overview

AI Pipeline Health Reporter is a no-code Sales Operations automation project designed to simulate the type of weekly reporting workflows commonly used by Revenue Operations and Sales Operations teams.

The system automatically analyzes pipeline KPIs, generates executive insights using AI, and emails a stakeholder-ready report.

Built using:

- Google Sheets
- Make.com
- OpenAI
- Gmail

---

## Architecture

```text
Scheduler
    ↓
Google Sheets
    ↓
OpenAI
    ↓
Gmail
```

Every week, the workflow:

1. Retrieves pipeline KPIs from Google Sheets.
2. Sends the metrics to OpenAI.
3. Generates an executive summary and recommendations.
4. Emails the report to stakeholders.

---

## Features

- Automated weekly reporting
- AI-generated executive summaries
- Pipeline health analysis
- Risk identification
- Actionable recommendations
- Email delivery via Gmail
- No-code implementation

---

## KPI Metrics

The system analyzes:

- Win Rate
- Average Deal Size
- Average Days Open
- Total Pipeline Value
- Closed Revenue
- Total Opportunities
- Stale Opportunities (>30 days)

---

## Data Source

Mock CRM opportunity data is stored in Google Sheets.

Example opportunity fields:

| Field |
|---------|
| Opportunity ID |
| Company |
| Industry |
| Region |
| Stage |
| Amount |
| Source |
| Rep |
| Created Date |
| Close Date |
| Days Open |
| Closed Won |
| Next Step |

---

## Dashboard Metrics

Google Sheets formulas are used to calculate pipeline KPIs.

### Win Rate

```excel
=COUNTIF(mock_sales_pipeline!L2:L,"Yes")/COUNTA(mock_sales_pipeline!B2:B)
```

### Average Deal Size

```excel
=AVERAGE(mock_sales_pipeline!F2:F)
```

### Average Days Open

```excel
=AVERAGE(mock_sales_pipeline!K2:K)
```

### Total Pipeline Value

```excel
=SUM(mock_sales_pipeline!F2:F)
```

### Closed Revenue

```excel
=SUMIF(mock_sales_pipeline!L2:L,"Yes",mock_sales_pipeline!F2:F)
```

### Total Opportunities

```excel
=COUNTA(mock_sales_pipeline!A2:A)
```

### Stale Opportunities

```excel
=COUNTIF(mock_sales_pipeline!K2:K,">30")
```

---

## Make Scenario

### Module 1

**Scheduler**

Runs weekly.

---

### Module 2

**Google Sheets**

Retrieves KPI values from the `KPIs` worksheet.

---

### Module 3

**OpenAI**

Uses GPT to analyze pipeline performance and generate:

- Executive Summary
- Key Risks
- Positive Trends
- Recommendations
- Action Items

---

### Module 4

**Gmail**

Emails the report to stakeholders.

---

## AI Prompt

```text
You are a Sales Operations Analyst.

Analyze the following weekly pipeline KPIs.

Win Rate:
{{A2}}

Average Deal Size:
{{B2}}

Average Days Open:
{{C2}}

Total Pipeline:
{{D2}}

Closed Revenue:
{{E2}}

Total Opportunities:
{{F2}}

Provide:

1. Executive Summary

2. Key Risks

3. Positive Trends

4. Recommendations

5. Action Items

Write this like a report to a VP of Sales.

Be specific and identify:

- Revenue risks
- Pipeline bottlenecks
- Opportunity aging concerns
- Positive performance indicators
- Areas requiring immediate attention

Use concise business language and bullet points where appropriate.
```

---

## Example Output

### Executive Summary

Pipeline health remains stable, although opportunity aging indicates potential bottlenecks.

### Key Risks

- 81 opportunities have remained open longer than 30 days.
- Average sales cycle length remains elevated.

### Positive Trends

- Closed revenue exceeded targets.
- Average deal size remains strong.

### Recommendations

- Prioritize aging opportunities.
- Review proposal-stage conversion.
- Improve follow-up cadence.

### Action Items

- Conduct pipeline reviews with account executives.
- Focus on opportunities open longer than 30 days.

---

## Future Enhancements

### Historical Trend Analysis

Track week-over-week performance:

- Win Rate Trends
- Revenue Growth
- Sales Cycle Changes
- Pipeline Growth

### CRM Integration

Replace Google Sheets with:

- HubSpot
- Salesforce
- Pipedrive

### Slack Notifications

Send alerts when:

- Win rate declines
- Stale opportunities exceed thresholds
- Pipeline coverage changes significantly

### Dashboard Visualization

Build executive dashboards using:

- Looker Studio
- Power BI
- Tableau

---

## Resume Bullet

> Built an AI-powered Sales Operations reporting workflow using Google Sheets, Make, OpenAI, and Gmail to automate KPI analysis, identify pipeline risks, and generate executive-level weekly reports.

