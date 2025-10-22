# Azure Function App Deployment Workflow

This GitHub Actions workflow automates the deployment of an Azure Function App, including infrastructure provisioning and code deployment.

## Overview

The workflow consists of two main jobs:
1. **deploy-infrastructure**: Checks for and creates required Azure resources if they don't exist
2. **deploy-function-code**: Deploys the function app code to Azure

## Prerequisites

Before using this workflow, you need to:

1. **Azure Subscription**: Have an active Azure subscription
2. **Azure Service Principal**: Create a service principal with contributor access to your subscription
3. **GitHub Secret**: Add `AZURE_CREDENTIALS` secret to your repository

### Creating Azure Service Principal

Run the following Azure CLI command to create a service principal:

```bash
az ad sp create-for-rbac --name "github-actions-sp" \
  --role contributor \
  --scopes /subscriptions/{subscription-id} \
  --sdk-auth
```

Copy the JSON output and add it as a secret named `AZURE_CREDENTIALS` in your GitHub repository (Settings → Secrets and variables → Actions → New repository secret).

## Configuration

The workflow uses the following environment variables (configured in the workflow file):

| Variable | Default Value | Description |
|----------|---------------|-------------|
| `AZURE_FUNCTIONAPP_NAME` | `skynet-func-app` | Name of the Azure Function App |
| `RESOURCE_GROUP` | `rg-blob-func-dev` | Azure Resource Group name |
| `LOCATION` | `eastus` | Azure region for deployment |
| `STORAGE_ACCOUNT` | `skynetstorageacct` | Storage account name (must be globally unique) |
| `RUNTIME` | `dotnet` | Function App runtime |
| `FUNCTIONS_VERSION` | `4` | Azure Functions version |

### Customizing Configuration

To customize these values for your deployment:

1. Edit `.github/workflows/deploy-function.yml`
2. Update the `env:` section at the top of the file
3. Ensure the `STORAGE_ACCOUNT` name is globally unique (lowercase letters and numbers only, 3-24 characters)

## Workflow Features

### Infrastructure Provisioning

The workflow automatically checks for and creates the following Azure resources if they don't exist:

- **Resource Group**: Creates the resource group if it doesn't exist
- **Storage Account**: Creates a storage account required by the Function App
- **Function App**: Creates the Function App with the specified configuration

### Smart Deployment

- **Idempotent**: The workflow can be run multiple times safely - it only creates resources that don't exist
- **Conditional Steps**: Each resource creation step only runs if the resource is not found
- **Verification**: After deployment, the workflow verifies that the Function App exists

### Code Deployment

The second job handles code deployment:

- Checks out the repository code
- Sets up the .NET environment
- Authenticates with Azure
- Deploys the function code (currently a placeholder - customize based on your project)

## Usage

### Automatic Deployment

The workflow runs automatically on:
- Push to the `main` branch

### Manual Deployment

You can also trigger the workflow manually:

1. Go to your repository on GitHub
2. Navigate to Actions → Deploy Azure Function App
3. Click "Run workflow"
4. Select the branch and click "Run workflow"

## Customizing Code Deployment

The code deployment step is currently a placeholder. To deploy your actual function code:

1. Uncomment the deployment commands in the `Build and deploy function code` step
2. Update the paths to match your project structure
3. If using a different runtime (e.g., Node.js, Python), update the setup step accordingly

### Example for .NET Functions

```yaml
- name: Build and deploy function code
  run: |
    # Navigate to your function app directory
    cd path/to/your/function
    
    # Build the function app
    dotnet build --configuration Release
    
    # Publish the function app
    dotnet publish --configuration Release --output ./output
    
    # Create a zip package
    cd output
    zip -r ../function-app.zip .
    cd ..
    
    # Deploy to Azure Function App
    az functionapp deployment source config-zip \
      --resource-group ${{ env.RESOURCE_GROUP }} \
      --name ${{ env.AZURE_FUNCTIONAPP_NAME }} \
      --src function-app.zip
```

### Example for Node.js Functions

```yaml
- name: Setup Node.js
  uses: actions/setup-node@v3
  with:
    node-version: '18.x'

- name: Build and deploy function code
  run: |
    # Navigate to your function app directory
    cd path/to/your/function
    
    # Install dependencies
    npm ci
    
    # Build the function app
    npm run build
    
    # Create a zip package
    zip -r function-app.zip .
    
    # Deploy to Azure Function App
    az functionapp deployment source config-zip \
      --resource-group ${{ env.RESOURCE_GROUP }} \
      --name ${{ env.AZURE_FUNCTIONAPP_NAME }} \
      --src function-app.zip
```

## Troubleshooting

### Common Issues

**Issue**: "Could not find function app in resource group"
- **Solution**: This workflow creates the function app if it doesn't exist. Ensure `AZURE_CREDENTIALS` secret is configured correctly.

**Issue**: "Storage account name must be between 3 and 24 characters"
- **Solution**: Update the `STORAGE_ACCOUNT` environment variable to meet Azure naming requirements.

**Issue**: "The subscription is not registered to use namespace 'Microsoft.Web'"
- **Solution**: Register the resource provider:
  ```bash
  az provider register --namespace Microsoft.Web
  ```

**Issue**: "Storage account name already taken"
- **Solution**: Storage account names must be globally unique. Choose a different name in the `STORAGE_ACCOUNT` environment variable.

### Viewing Logs

To view detailed logs:
1. Go to Actions tab in your GitHub repository
2. Click on the workflow run
3. Click on a specific job to see detailed logs

## Security Best Practices

1. **Never commit secrets**: Always use GitHub Secrets for sensitive information
2. **Principle of least privilege**: Grant the service principal only necessary permissions
3. **Rotate credentials**: Regularly rotate your Azure service principal credentials
4. **Review access**: Periodically review who has access to your GitHub repository secrets

## Additional Resources

- [Azure Functions Documentation](https://docs.microsoft.com/en-us/azure/azure-functions/)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Azure CLI Documentation](https://docs.microsoft.com/en-us/cli/azure/)
- [Deploying to Azure Functions with GitHub Actions](https://docs.microsoft.com/en-us/azure/azure-functions/functions-how-to-github-actions)
