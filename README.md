# About this GitHub action

## Introduction
The intention is to allow Salesforce clients to publish GitHub content to Salesforce Knowledge Base.
The user receives credentials when creating a GitHub connector in Salesforce.

## Ingested content
Zips all the files

## Processed content
- Markdown files
- HTML files

## Before using the Action
Ensure that those secrets are added:

1. On GitHub, navigate to the main page of the repository.
2. Under your repository name, click  Settings. If you cannot see the **"Settings"** tab, select the dropdown menu, then click Settings.
    ![]([http://codekeyboards.com/img/code-104-bright-backlit.jpg](https://github.com/user-attachments/assets/2dacddb0-f744-461a-a37f-b01d0d1ca476))
3. In the **"Security"** section of the sidebar, select **Secrets and variables**, then click Actions.<br/><img width="347" alt="Screenshot 2024-09-05 at 10 16 17" src="https://github.com/user-attachments/assets/b4ab13e7-b539-4f44-bf69-6cac3e0f9540">
<br/>
5. Click on **"Manage environment secrets"**.<br/><img width="822" alt="Screenshot 2024-09-05 at 10 21 32" src="https://github.com/user-attachments/assets/1f2599c9-4b1f-447c-86c6-402e9b592d5c"><br/><img width="815" alt="Screenshot 2024-09-05 at 10 24 49" src="https://github.com/user-attachments/assets/e4645704-4a9c-448e-9d75-3762e4211480"><br/>


### The next secrets should be added:
- AWS_KEY_ID
- AWS_SECRET_ACCESS_KEY
- AWS_REGION
- AWS_BUCKET
- AWS_FOLDER
