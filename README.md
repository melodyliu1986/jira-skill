# Jira Skill for Gemini CLI

This is a specialized skill for [Gemini CLI](https://github.com/google/gemini-cli) that allows the agent to interact with Jira tickets at `https://redhat.atlassian.net`.

## Features
- **Fetch & Summarize**: Get clean, Markdown-formatted summaries of Jira issues.
- **ADF Parsing**: Automatically converts complex Atlassian Document Format (ADF) into readable text.
- **Field Awareness**: Pulls in standard fields (Status, Reporter, Assignee, Parent) and relevant Custom Fields (Target Dates, Blocked status, etc.).
- **Comment Support**: Ability to add comments to Jira tickets directly from the CLI.

## Security & Credentials
This skill uses the **`pass`** (Unix password manager) to store and retrieve credentials securely. It never stores your plain-text token or email in the code.

### Setup Instructions
1. **Store your credentials** in your local `pass` store:
   ```bash
   echo "your-actual-api-token" | pass insert -e redhat/jira-token
   echo "your-email@redhat.com" | pass insert -e redhat/jira-email
   ```
2. **Install the skill** in Gemini CLI:
   ```bash
   gemini skills install https://github.com/melodyliu1986/jira-skill
   ```
3. **Reload Skills**:
   In your Gemini CLI session, run:
   ```bash
   /skills reload
   ```

## Usage
- "Gemini, summarize GITOPS-8825"
- "Gemini, check the status and reporter of GITOPS-8826"
- "Gemini, add a comment to GITOPS-123 saying 'This is fixed in the latest PR'"
