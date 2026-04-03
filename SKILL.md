---
name: jira-skill
description: Interacts with Jira tickets on https://redhat.atlassian.net. Use when fetching, summarizing, or managing tickets.
---

# Jira Skill

This skill allows Gemini CLI to interact with Jira issues at `https://redhat.atlassian.net`.

## Prerequisites

- **Authentication**: Set the following environment variables:
  - `JIRA_URL`: Defaults to `https://redhat.atlassian.net`
  - `JIRA_EMAIL`: Your Red Hat email address.
  - `JIRA_API_TOKEN`: Your Jira API token.

## Tools

- `scripts/jira_client.py get_issue <ISSUE-KEY>`: Fetches ticket details (summary, description, status, assignee) as a JSON object.
- `scripts/jira_client.py add_comment <ISSUE-KEY> "<COMMENT>"`: Adds a comment to the specified issue.

## Usage Guidelines

1. **Summarization**: Use `get_issue` to fetch data, then provide a concise summary or extract action items.
2. **Commentary**: After a task (like code refactoring or bug investigation), you can use `add_comment` to update the Jira ticket.
3. **Status Check**: Use `get_issue` to verify the current status or assignee before starting work.
