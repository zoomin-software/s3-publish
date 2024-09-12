# 🚀 About this GitHub action

## Introduction
The intention is to allow Salesforce clients to publish GitHub content to Salesforce Knowledge Base.  
The user receives credentials when creating a GitHub connector in Salesforce.  

## Ingested content
Zips all the files

## Processed content
- Markdown files
- HTML files

## 🤖 Works when
A pull request is created.  
Branches: `main`, `master`.  

## 💡 Before using the Action
Ensure that those secrets are added:

1. On GitHub, navigate to the main page of the repository.
2. Under your repository name, click  Settings. If you cannot see the **"Settings"** tab, select the dropdown menu, then click Settings.
    ![](https://github.com/user-attachments/assets/2dacddb0-f744-461a-a37f-b01d0d1ca476)
3. In the **"Security"** section of the sidebar, select **Secrets and variables**, then click Actions.
    ![](https://github.com/user-attachments/assets/b4ab13e7-b539-4f44-bf69-6cac3e0f9540)
4. Click on **"Manage environment secrets"**.
    ![](https://github.com/user-attachments/assets/1f2599c9-4b1f-447c-86c6-402e9b592d5c)
    ![](https://github.com/user-attachments/assets/e4645704-4a9c-448e-9d75-3762e4211480)


### 🔑 The next secrets should be added:
- `AWS_KEY_ID`
- `AWS_SECRET_ACCESS_KEY`
- `AWS_REGION`
- `AWS_BUCKET`
- `AWS_FOLDER`

## 💻 Usage example
```yaml
name: Action Name
on: [push]

jobs:
  deploy:
    name: Upload to Amazon S3
    runs-on: ubuntu-latest
    # These permissions are needed to interact with GitHub's OIDC Token endpoint.
    permissions:
      id-token: write
      contents: read
    steps:  
      - name: Github Uploader for Salesforce Unified Knowledge
        uses: zoomin-software/s3-publish@v0.2.0
        with:
          aws-key-id: ${{ secrets.AWS_KEY_ID }}
          aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          aws-region: ${{ secrets.AWS_REGION }}
          aws-bucket: ${{ secrets.AWS_BUCKET }}
          aws-folder: ${{ secrets.AWS_FOLDER }}
```
