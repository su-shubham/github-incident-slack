# 🚀 GitHub Issues to Slack Notification & Resolve Actions Pipeline

Streamline your team's workflow and improve issue resolution with this automated pipeline. This pipeline continuously monitors GitHub for issues tagged as "bug" 🐞 or "enhancement" ⚙️, sends alerts to a Slack channel with detailed issue information, and even generates an AI-based response with potential solutions. By integrating GitHub, Slack, and Cohere AI, your team can stay informed and resolve issues faster and more efficiently.

## 📄 Pipeline Overview
1. **Monitor GitHub**: Keep track of issues labeled as "bug" or "enhancement" in your repository.
2. **Notify Slack**: Alert your Slack channel with key details about the detected issue.
3. **Generate AI Suggestions**: Use AI to generate a suggested solution to the issue.
4. **Share AI Response**: Send the AI-generated response back to the Slack channel for team review.

### 🛠️ Components Breakdown
1. **GitHub Monitor Issues (`github-monitor-issues`)**:
   - **Type**: GitHub Component
   - **Task**: `TASK_LIST_ISSUES`
   - **Function**: Scans the repository for issues with specific labels.

2. **Slack Notify Issues (`slack-notify-issues`)**:
   - **Type**: Slack Component
   - **Task**: `TASK_WRITE_MESSAGE`
   - **Function**: Sends an alert to a specified Slack channel when an issue is found.

3. **AI Generate Response (`ai-generate-response`)**:
   - **Type**: Cohere Component
   - **Task**: `TASK_TEXT_GENERATION_CHAT`
   - **Function**: Creates a detailed AI-generated solution to the issue.

4. **Slack Send AI Suggestion (`slack-send-ai-suggestion`)**:
   - **Type**: Slack Component
   - **Task**: `TASK_WRITE_MESSAGE`
   - **Function**: Shares the AI-generated response in the Slack channel.

## 📸 Visual Demo
Check out the visual representation of this workflow:

| <img src="https://github.com/user-attachments/assets/b073ba59-17c5-4594-bb0c-518144131adc" width="500" /> | <img src="https://github.com/user-attachments/assets/ccbcdba2-e2b2-4268-84b0-a3f59f3ccebf" width="500" /> |
|:----------------------------------------------------------------------------------------------------------:|:----------------------------------------------------------------------------------------------------------:|

| <img src="https://github.com/user-attachments/assets/d8b4a7e4-3e33-4c34-b7f0-6b59b6005c58" width="500" /> | <img src="https://github.com/user-attachments/assets/3e059613-cc90-4a8f-a071-91a73e17227c" width="500" /> |
|:----------------------------------------------------------------------------------------------------------:|:----------------------------------------------------------------------------------------------------------:|



## 📦 Variables

| Variable               | Description                                  | Format   | UI Order |
|------------------------|----------------------------------------------|----------|----------|
| `repository_owner`     | The owner (username or organization) of the GitHub repository. | string   | 1        |
| `repository_name`      | The name of the GitHub repository to monitor. | string   | 2        |
| `slack_channel_name`   | The Slack channel where incident notifications will be sent. | string   | 3        |

## ⚙️ Configuration Steps

### 1. Set Up Secrets
Before running the pipeline, ensure you have added the following secrets to your Instill AI project:
- **`github-access-token`**: GitHub API token with `repo` or `read:org` permissions.
- **`slack-bot-token`**: Slack bot token with `chat:write` permission.
- **`cohere`**: Cohere API key for AI text generation.

### 2. Run the Pipeline
Use the Instill AI Pipeline Playground to execute the pipeline. Input the necessary variables (`repository_owner`, `repository_name`, `slack_channel_name`) and ensure the secrets are correctly configured.

## 📝 Example Workflow
1. **Monitor**: The pipeline starts by monitoring the specified GitHub repository for issues labeled "bug" or "enhancement."
2. **Notify**: If an issue is detected, it triggers a Slack notification containing the issue details.
3. **AI Generate**: The AI component produces a response with detailed suggestions for resolving the issue.
4. **Send AI Response**: The generated response is sent back to Slack for your team to review and take action.

## 🚦 Important Notes
- **Permissions**: Make sure your GitHub token has the necessary permissions (`repo` or `read:org`).
- **Slack Authorization**: Your Slack bot token should include the `chat:write` permission.
- **Customization**: You can customize the Cohere AI response settings as needed to better fit your use case.

---

Elevate your team's productivity and issue management with this fully automated, integrated pipeline, turning issue tracking and resolution into a seamless process.
