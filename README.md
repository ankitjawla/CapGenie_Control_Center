# CapGenie Control Center

A Streamlit app for integrating JIRA Cloud and GitHub, powered by Azure OpenAI.  
Generate user stories, subtasks, implementation code, and test cases, then automatically create JIRA issues and push code to GitHub.

---

## Features

- **JIRA Cloud Integration:**  
  Authenticate and connect to your Atlassian JIRA Cloud instance.  
  Create issues and subtasks directly from the app.

- **GitHub Integration:**  
  List your repositories, clone them, create feature branches, and push generated code and tests.

- **AI-Powered Content Generation:**  
  Uses Azure OpenAI to generate detailed JIRA issue descriptions, development subtasks, Python implementation code, and test cases from a user story prompt.

---

## Setup

### 1. Clone the repository

```sh
git clone <this-repo-url>
cd CapGenie_Control_Center
```

### 2. Configure environment variables

Create a `.env` file in the project root with the following variables (see `.env` for example):

```env
AZURE_OPENAI_ENDPOINT=...
AZURE_OPENAI_API_KEY=...
AZURE_OPENAI_API_VERSION=...
AZURE_OPENAI_DEPLOYMENT=...

GITHUB_USERNAME=...
GITHUB_TOKEN=...

JIRA_INSTANCE_URL=...
JIRA_USERNAME=...
JIRA_API_TOKEN=...
```

### 3. Install requirements

```sh
pip install -r requirements.txt
```

### 4. Run the app

```sh
streamlit run streamlit_app.py
```

---

## Usage

1. **Connect to JIRA:**  
   The app will validate your JIRA credentials and list available projects.

2. **Select Project and Issue Type:**  
   Choose a JIRA project and issue type for your user story.

3. **Select GitHub Repository:**  
   Pick a repository from your GitHub account.

4. **Enter User Story:**  
   Provide a user story in the text area.

5. **Generate and Create:**  
   - The app will use Azure OpenAI to generate:
     - JIRA issue description
     - Development subtask description
     - Python implementation code
     - Test cases
   - It will create the main issue and a subtask in JIRA.
   - It will create a feature branch in your selected GitHub repo, add the generated code and tests, commit, and push the changes.

---

## Notes

- **JIRA:** Only works with Atlassian Cloud (URL must end with `.atlassian.net`).
- **GitHub:** Requires a personal access token with repo permissions.
- **Azure OpenAI:** Requires access to Azure OpenAI and a valid deployment.

---

## License

Apache License 2.0.
