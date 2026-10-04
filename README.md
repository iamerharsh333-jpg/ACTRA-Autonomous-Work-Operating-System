Setup & Run Instructions
Prerequisites
- Node.js 22+
- n8n
- Google Gemini API access
- Supabase project
- GitHub API access
- Browser Use account/API access for browser automation
1. Install and Start n8n
nvm use 22
n8n



2. Import the ACTRA Workflow
1. Open n8n.
2. Select Import from File.
3. Import:
workflow/ACTRA_workflow.json

4. Open the imported workflow.
3. Configure Credentials
Configure your own credentials in n8n for:
- Google Gemini
- GitHub
- Browser Use
- Supabase
No API keys, OAuth tokens, or secrets are included in this repository.

4. Configure Supabase
Create the required agent_runs table and configure the Supabase REST connection used by the ACTRA workflow.
The workflow uses Supabase to persist execution records outside the n8n runtime.
5. Activate the Workflow
In n8n:
Save → Publish/Activate
The workflow can then receive a natural-language goal through the ACTRA chat interface or webhook.
6. Run ACTRA
Example:
Prepare tomorrow's ACTRA product launch. Use the available company context and policies, inspect the GitHub repository, create the necessary internal launch tasks, persist the execution to Supabase, and independently verify the same record. Do not send external communications or make irreversible changes.

ACTRA will:
Goal
 ↓
Understand
 ↓
Plan
 ↓
Select tools
 ↓
Execute
 ↓
Observe
 ↓
Recover if needed
 ↓
Persist state
 ↓
Independently verify
 ↓
Complete

Security
Before running the workflow, replace all example credentials with your own credentials.
Never commit:
- API keys
- OAuth tokens
- Supabase secret/service-role keys
- Private credentials
- .env files
- Confidential company data
The repository contains only the sanitized workflow configuration and documentation.
