# PBI-Embedded-App-Owns-Data-Row-Level-Security-Filtering

## SDKs available for Power BI Embedded
Power BI provides for the following:
1. .Net Framework
2. .Net Core
3. Java
4. Node JS
5. Python

### Steps
1. Set authentication method (choose Master User and not Service Principal)
2. Register Power BI app in Azure Active Directory (Azure AD)
3. Auntheticate app using either Service Principal or Username/password
4. Generate access token (Embed Token API - A Power BI REST API)
5. Embed report in portal/app

#### Key Aunthetication Params from Azure AD App Registration
These strings are provided after app registration.
They include:
1. Display name (Service Principal name)
2. Application (client} ID
3. Directory (tenant) ID
4. Client secret

## The Embed Token API Documentation

Generates an embed token to view the specified dashboard from the specified workspace.

### Required Scope
All of the following:

  Dashboard.ReadWrite.All or Dashboard.Read.All
  Report.ReadWrite.All or Report.Read.All
  Dataset.ReadWrite.All or Dataset.Read.All

#### HTTP 
POST "https://api.powerbi.com/v1.0/myorg/groups/{groupId}/dashboards/{dashboardId}/GenerateToken"

##### URI Parameters
1. dashboardId
2. groupId

