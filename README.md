# Salesforce Knowledge Article Connector for GitHub

## About This Connector

The GitHub Connector for Salesforce Unified Knowledge allows you to upload your GitHub repository supported contents to Salesforce as Knowledge Articles.  
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

## What to Do Next?
Follow the instuctions [here](https://unifiedknowledge.ai/salesforce/bundle/github/page/github_markdown_as_a_unified_knowledge_source.html).
