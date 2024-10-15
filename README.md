# Salesforce Knowledge Article Connector for GitHub

## About This Connector

The GitHub Connector for Salesforce Unified Knowledge, allows you to upload your GitHub repository supported contents to Salesforce as Knowledge Articles.  
Once in Salesforce, those knowledge articles can be natively viewed and searched, and grounded on by Einstein.
This connector is used with the following [documentation](https://unifiedknowledge.ai/salesforce/bundle/github/page/github_markdown_as_a_unified_knowledge_source.html), so if you’re just getting started begin there. 
You should come to this page only when you have reached the steps [here](https://unifiedknowledge.ai/salesforce/bundle/github/page/configure_github_markdown_as_a_unified_knowledge_source.html).

## Upload Process
When the connector runs, a zip file of the repo contents which can be uploaded is created and the files are uploaded to Salesforce. 

## Supported File Types

Only the following file types are supported. 
- Markdown 
- HTML 

## Automation Trigger

The connector is automatically triggered when a pull request is created from the following branches: `main` and/or `master`.  

## How to Add the GitHub Secrets

Before running the connector, you need to add a few GitHub secrets to authorize and authenticate you with Salesforce. 

1. On GitHub, navigate to the main page of the repository.
2. Under your repository name, click  **Settings**. If you cannot see the **Settings** tab, select the dropdown menu, then click **Settings**.
    ![](https://github.com/user-attachments/assets/2dacddb0-f744-461a-a37f-b01d0d1ca476)
3. In the **"Security"** section of the sidebar, select **Secrets and variables**, then click **Actions**.
    ![](https://github.com/user-attachments/assets/b4ab13e7-b539-4f44-bf69-6cac3e0f9540)
4. Click on **Manage environment secrets**. 
    ![](https://github.com/user-attachments/assets/1f2599c9-4b1f-447c-86c6-402e9b592d5c)
    ![](https://github.com/user-attachments/assets/e4645704-4a9c-448e-9d75-3762e4211480)
5. Add the GitHub secrets using the values you obtained from [Salesforce Unified Knowledge, step 7](https://unifiedknowledge.ai/salesforce/bundle/github/page/configure_github_markdown_as_a_unified_knowledge_source.html).


### Map Unified Knowledge Values to GitHub
To create a secret you need to use the values you obtained from Unified Knowledge. As the values from Unified Knowledge differ slightly, use the following table to align them.

| Unified Knowledge | GitHub |
| --- | --- |
| bucket: | AWS_BUCKET |
| folder: |  AWS_DIRNAME  |
 |  accessKeyId: |  AWS_KEY_ID |
| secretAccessKey: | AWS_SECRET_ACCESS_KEY |
 |  region: |  AWS_REGION |


## Sample Script

When instructed, in these [directions](https://unifiedknowledge.ai/salesforce/bundle/github/page/prepare_your_github_repository.html#PrepareYourGitHubRepository-Step2_CreateaGitHubWorkflow), you can use the following sample script, modifying it to suit your needs. 

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
