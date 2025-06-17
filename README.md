As part of our DevOps automation, I built a Python script that triggered an API call to Terraform Cloud from an Azure DevOps pipeline. 
The script used the Terraform Cloud API to update versioned environment variables (like org_version, website_version, etc.) inside a Terraform workspace.

This was necessary because I use versioning across modules and deployments, and wanted to automate this update before triggering a Terraform plan/apply. 
The script authenticated using a bearer token, made PATCH calls to Terraform Cloud, and updated each relevant variable with the new version we were deploying.
