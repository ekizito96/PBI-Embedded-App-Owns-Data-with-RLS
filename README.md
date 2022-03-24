# PBI-Embedded-App-Owns-Data-Row-Level-Security-Filtering

## (A) SDKs available for Power BI Embedded
Power BI provides for the following:
1. .Net Framework
2. .Net Core
3. Java
4. Node JS
5. Python


## (B) Using .Net Framework
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

