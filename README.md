
# Building and Deploying ASP.NET Core on Azure App Service

This project demonstrates how to deploy an ASP.NET Core application on **Azure App Service**. Azure App Service is a fully managed platform for building, deploying, and scaling web applications, REST APIs, and mobile backends. This guide walks you through deploying an ASP.NET Core console application to App Service on Linux.

---

## Project Contents

- **ConsoleApp1**: Source code for the ASP.NET Core application.
- **azure-pipelines.yml**: Configuration for Azure Pipelines to automate build and deployment.
- **.github/workflows**: GitHub Actions workflow for building and deploying the app to Azure App Service.

---

## Problem Statement

Create an ASP.NET Core application and host it on Azure App Service for Linux.

---

## Pre-requisites

- Install **Git**: [Download and install Git](https://git-scm.com/)
- Install **.NET Core SDK**: [Download and install .NET Core SDK](https://dotnet.microsoft.com/download)

---

## Steps to Perform

### 1. Create the App Locally
- Open **Visual Studio** and install the required `.NET` extension if not already installed.
  ![image](https://github.com/user-attachments/assets/fd80a262-2149-4e17-97ab-666b97bb0eea)

- Create a new project and select the `Console App` template.
- Customize the `Program.cs` file as needed.
```
Console.WriteLine("Hello, World!");
Console.WriteLine("The current time is " + DateTime.Now);
```
- Save the project locally.

### 2. Run the App Locally
- Build and test the app using Visual Studio to ensure it runs correctly.
![image](https://github.com/user-attachments/assets/9c6e7ece-e545-423d-8852-c5b274993505)

### 3. Push to GitHub
- Open **GitBash** and navigate to the project folder.
- Initialize a Git repository and push the project to GitHub using the following commands:
  ```bash
  git init
  git add .
  git commit -m "Initial commit"
  git branch -M main
  git remote add origin https://github.com/<your-username>/<your-repository>.git
  git push -u origin main
  ```
![image](https://github.com/user-attachments/assets/69a892ae-e8b4-496e-9cb3-3033613ae549)
![image](https://github.com/user-attachments/assets/006a5c6e-8f08-4650-a0aa-ff6741845087)
![image](https://github.com/user-attachments/assets/b87a9c58-97fe-4f48-89f2-87ee531653aa)


### 4. Deploy to Azure
- Navigate to the Azure portal and create a new **Web App** in the **App Services** section.
- Configure a resource group, App Service plan, and Web App using the portal.
![image](https://github.com/user-attachments/assets/e5be3d87-5608-407b-89ab-8229f8c80a3a)
![image](https://github.com/user-attachments/assets/4cfaac00-f008-4135-affa-457c4a8c6962)

- Set up a deployment:
- Use the **Deployment Center** in Azure App Service to connect the GitHub repository for deployment.
  - GitHUb account
  - organization
  - repository
  - Branch
  
![image](https://github.com/user-attachments/assets/2d287e69-58fe-43fa-b203-9feef06b33ce)
![image](https://github.com/user-attachments/assets/e5f07a4f-4f24-4139-897d-728b6c3c47e1)



### 5. Manage and Update the App
- After deployment, verify the app is running by visiting the App Service URL.
- Update the `Program.cs` file, commit the changes, and push them to GitHub. Azure will automatically redeploy the updated app.
![image](https://github.com/user-attachments/assets/99ec89be-e5f9-4006-9008-cb44456929a5)
![image](https://github.com/user-attachments/assets/14dba215-f593-41ae-9a3c-a758dbe62919)
![image](https://github.com/user-attachments/assets/cdf91685-b85f-407c-8a0e-1a3fe326db47)

### 6. Clean Up Resources
- To avoid unnecessary charges, delete the App Service, resource group, and other associated resources when no longer needed.

---

## Deployment Workflow

This project uses **Azure Pipelines** for CI/CD. The `azure-pipelines.yml` file configures the pipeline to:
1. Build the .NET Core application.
2. Deploy the app to Azure App Service.

Alternatively, a GitHub Actions workflow is provided in the `.github/workflows` directory.

---

## Project Structure

```
Venkat-Narayan-07/
├── .github/workflows/        # GitHub Actions workflows
├── ConsoleApp1/              # Source code for the ASP.NET Core application
├── ConsoleApp1.sln           # Visual Studio solution file
├── azure-pipelines.yml       # Azure Pipelines configuration
```

---

## Resources

- [Azure App Service Documentation](https://learn.microsoft.com/en-us/azure/app-service/)
- [Deploy ASP.NET Core apps to Azure](https://learn.microsoft.com/en-us/aspnet/core/host-and-deploy/azure-apps/)
- [Azure Pipelines Documentation](https://learn.microsoft.com/en-us/azure/devops/pipelines/)
- [GitHub Actions for Azure](https://github.com/Azure/actions)

---

## Author

[Venkat Narayan](https://github.com/Venkat-Narayana-16)
