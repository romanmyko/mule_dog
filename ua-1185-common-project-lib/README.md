# Install project
## 1. Import project

## 2. Run in ~/common-project
```bash
mvn clean package install:install
```

## 3. Add dependency to pom.xml data to insert in project pom.xml

### a.
```plaintext
/home/******n/.m2/repository/com/mycompany/common-project/maven-metadata-local.xml
```

```
<metadata>
  <groupId>com.mycompany</groupId>
  <artifactId>common-project</artifactId>
  <versioning>
    <versions>
      <version>1.0.0-SNAPSHOT</version>
    </versions>
    <lastUpdated>20240701100303</lastUpdated>
  </versioning>
</metadata>
```
### b. Add in pom.xml
```xml
<dependency>
  <groupId>com.mycompany</groupId>
  <artifactId>common-project</artifactId>
  <version>1.0.0-SNAPSHOT</version>
  <classifier>mule-plugin</classifier>
</dependency>
```
## 4. Add in global config 
- import(configuration) name imported flow (ua-****-error.xml)

###  a) min import json out
  ├── ua-1185-spacex-common-project-config.xml
  ├── ua-1185-spacex-common-project-sender.xml
  ├── ua-1185-spacex-common-project-impl.xml
  └── ua-1185-spacex-main-error.xml

###  a) min import xml out
  ├── ua-1185-spacex-common-project-config.xml
  ├── ua-1185-spacex-common-project-sender.xml
  ├── ua-1185-spacex-common-project-xml-impl.xml
  └── ua-1185-spacex-main-error.xml

## 5. Add in Run 
```In Mule RUN

-M-Ddogkey=*****54929 
-M-Ddoghost=datadoghq.eu
-M-DAZURE_CLIENT_ID=1a7d48c******85c8fbfd5
-M-DAZURE_TENANT_ID=b00a1ab0--*******55-d2019c39f914
-M-DAZURE_CLIENT_SECRET=nn38Q~lhmb1qb******RdkoaN4 
-M-DMULE_AZURE_KEY_VAULT_NAME=******

```
## 6. Restart project

# Project structure

# This is a sample completion of the task

## Dependency structure task
```structure
ua-1185-spacex-<name>-error.xml (ua-1185-spacex-api-error.xml)
├── Error handler (ua-1185-spacex-api-Error_Handler)
│   ├── Error Continue / Error Propagate
│   ├── code error: 404
│   └── Type error: HTTP: NOT_FOUND
├── Error description: Error was received during creation process for new Launch
│   └── Source error: Launch externalId: '12412424'
```
## Is the real structure of error handler
```structure
├── ua-1185-spacex-api-error.xml
   ├── ua-1185-spacex-APIKit-Error_Handler (flow)
   ├── ua-1185-spacex-api-Error_Handler  (flow)
├── ua-1185-spacex-db-error.xml
   ├── ua-1185-spacex-mysql-Error_Handler (flow)
├── ua-1185-spacex-common-project-api.xml
├── ua-1185-spacex-common-project-config.xml
├── ua-1185-spacex-common-project-impl.xml
└── ua-1185-spacex-main-error.xml
    ├── ua-1185-spacex-main-Error_Handler (flow)
```
## Table

| MuleSoft API Error Configuration File | Error handler Flow name          |Error Continue/Error Propagate|Code error|Type error      |description|source|
|---------------------------------------|----------------------------------|------------------------------|----------|----------------|----------|----------------|
| ua-1185-spacex-api-error.xml          | ua-1185-spacex-api-Error_Handler |        Error      Propagate  | 404      |HTTP: NOT_FOUND |

# Global to custom used var ERROR_MESSAGE =>  ua-1185-spacex-common-project-impl.xml
## Var Name
``` global var name 
ERROR_MESSAGE
```
## Var Structure
```var structure
%dw 2.0
output application/json
---
{
	"logType":"Error: ",
	"code": 503,
	"message": "Service Unavailable",
	"errorType": "DB:CONNECTIVITY",
	"dateTime": now(),
	"description": "Test description",
	"source": "Test source: 123456"
}
```


## Azure Keys

### Mail Key

``` mail repport
key-repport
{
'host': 'smtp.gmail.com',
'port': '587',
'user': '***.sppt@gmail.com',
'password': '*** vysf eihd uxao',
'fromaddres': '@gmail.com',
'toaddres': '@gmail.com'
}


key-repport-2
{
'host': 'smtp.gmail.com',
'port': '587',
'user': 'test',
'password': 'test test test',
'fromaddres': 'test@test',
'toaddres': 'test@test'
}

report-mail
{
'host': 'smtp.gmail.com',
'port': '587',
'user': 'test',
'password': 'test test test',
'fromaddres': 'test@test',
'toaddres': 'test@test'
}
```

### case Key
```
key-case
{
   'protocol': 'HTTP',
   'base-path': 'cases',
   'host': 'test',
   'port': '80',
   'password': '',
   'method': 'POST'
}
```
### DB Key

```
key-mongo
{
  'host': 'mongodb', 
  'user': 'admin',
  'password': '******',
  'cluster': '*****.servers.mongodirector.com:27017'
}
```

```
key-salesforce 
{
   'username': '******@gmail.com',
   'password': '*******',
   'securitytoken': '**********',
   'authorizationurl': 'https://login.salesforce.com/services/Soap/u/60.0'
}
```

```
key-sql
{
  "host": "S******.servers.mongodirector.com",
  "port": "3306",
  "user": "*****",
  "password": "******",
  "database": "******"
}

```