# Marketing Intelligence Operating System

The Marketing Intelligence Operating System is an agent-first way for a marketing, product, and website team to turn analytics questions into useful reporting work.

This is not a dashboard project yet. The first MVP is a structured intake system that helps the team clarify requests before anyone pulls data, creates a dashboard, or writes a leadership report.

## Why This Exists

Marketing reporting requests often start broad:

- "How did this page perform?"
- "Can we get a leadership-ready report?"
- "Did the campaign work?"
- "Are people clicking through to book?"

Those questions are reasonable, but they need structure before they can become reliable reporting. This system helps define the business question, audience, decision, metrics, likely data sources, caveats, and the right next reporting agent.

The goal is to reduce rework, avoid misleading reports, and make analytics output more useful for decision-making.

## Connection to the Design Operating System

The existing design operating system helps the team plan, create, and govern digital experiences. The Marketing Intelligence Operating System extends that work into measurement and interpretation.

Together, the systems support a complete loop:

Marketing initiative -> website/content execution -> telemetry plan -> data collection -> reporting -> AI interpretation -> recommendations -> next action

The design system helps create the experience. The intelligence system helps the team understand what happened after launch and what to do next.

## MVP Focus

The first MVP focuses on agent-based analytics intake.

Instead of jumping straight into data pulls or dashboards, the first agent converts vague analytics and reporting requests into structured Analytics Request Briefs. These briefs create a shared understanding of what the team is trying to answer, why it matters, what data may be needed, and what limitations should be considered.

## First Agent

### Marketing Analytics Intake Agent

The Marketing Analytics Intake Agent turns an initial analytics or reporting request into a practical brief.

It clarifies:

- The request summary
- The primary business question
- The reporting audience
- The decision the report supports
- Recommended metrics
- Likely data sources
- Required inputs
- Known data caveats
- Suggested reporting format
- The next agent to run

This agent should run before deeper reporting work begins.

## Future Agents

The following agents are future additions and are not part of the first MVP build:

- Data Source Mapping Agent
- Campaign Reporting Agent
- Page Performance Agent
- Tracking Health Agent
- Leadership Insight Agent

These agents will eventually help map available systems, analyze campaign and page performance, evaluate tracking quality, and turn reporting outputs into leadership-ready insights.

## Current MVP Structure

```text
marketing-intelligence-os/
  README.md
  agents/
    marketing-analytics-intake-agent.md
  tests/
    summer-offers-intake-test.md
  templates/
    analytics-request-brief-template.md
```

## How to Use This MVP

1. Start with a stakeholder analytics or reporting request.
2. Run the Marketing Analytics Intake Agent.
3. Review the resulting Analytics Request Brief.
4. Confirm missing inputs, caveats, and reporting expectations.
5. Use the brief to decide which reporting agent or analyst workflow should run next.

This keeps reporting grounded in a business question before the team invests time in analysis, dashboards, or leadership materials.
