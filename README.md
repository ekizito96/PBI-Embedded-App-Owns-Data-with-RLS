# PBI-Embedded-App-Owns-Data-Row-Level-Security-Filtering

## (A) SDKs available for Power BI Embedded
Power BI provides for the following:
1. .Net Framework
2. .Net Core
3. Java
4. Node JS
5. Python

## (B) Key Steps
1. Set authentication method (choose Master User and not Service Principal)
2. Register Power BI app in Azure Active Directory (Azure AD)
3. Auntheticate app using either Service Principal or Username/password
4. Generate access token (Embed Token API - A Power BI REST API)
5. Embed report in portal/app

### Key Aunthetication Params from Azure AD App Registration (Step 2 above)
These strings are provided after app registration.
They include:
1. Display name (Service Principal name)
2. Application (client} ID
3. Directory (tenant) ID
4. Client secret

## (C) The Embed Token API Documentation

Generates an embed token to view the specified dashboard from the specified workspace.

### Required Scope
All of the following:

 - Dashboard.ReadWrite.All or Dashboard.Read.All
 - Report.ReadWrite.All or Report.Read.All
 - Dataset.ReadWrite.All or Dataset.Read.All

###### **HTTP**
```
POST https://api.powerbi.com/v1.0/myorg/groups/{groupId}/dashboards/{dashboardId}/GenerateToken
```

#### **URI Parameters**
1. **dashboardId**      
  - *string uuid* 
     - *Set the Dashboard ID*
2. **groupId**          
  - *string uuid*
    - *Set the Workspace ID*

##### Example:

###### **REQUEST**
```
POST https://api.powerbi.com/v1.0/myorg/groups/f089354e-8366-4e18-aea3-4cb4a3a50b48/dashboards/69ffaa6c-b36d-4d01-96f5-1ed67c64d4af/GenerateToken
```

###### **REQUEST BODY**
```
{
  "accessLevel": "View",
  "identities": [
    {
      "datasets": [
        "cfafbeb1-8037-4d0c-896e-a46fb27ff229"
      ],
      "identityBlob": {
        "value": "eyJ0eX....AAA="
      }
    }
  ]
}
```

###### **RESPONSE**
```
Status code: 200
{
  "token": "H4sI....AAA=",
  "tokenId": "49ae3742-54c0-4c29-af52-619ff93b5c80",
  "expiration": "2018-07-29T17:58:19Z"
}
```



