# CloudHub Salesforce API #
## Endpoints ##
### Production ###
`http://ua-1185-salesforce-system-api.us-e2.cloudhub.io/`
### Local ###
`http://0.0.0.0:8081/`
## API Endpoints ##
### Update Salesforce Contract ###
**PUT /contracts**

Request

`PUT http://ua-1185-salesforce-system-api.us-e2.cloudhub.io/contracts`

Body

```json
[
    {
        "Id": "800Qy00000GZAmTIAX",
        "AccountId": "001Qy00000OJydlIAD",
        "ExternalId__c": "23334",
        "SuccessStatus__c": "1",
        "DateCreation__c": "2024-07-11",
        "Details__c": "Hello",
        "RocketName__c": "Rocket",
        "NameSalesforce__c": "Name",
        "Status": "Draft",
        "StartDate": "2023-06-24",
        "ContractTerm": 1
    }
]
```
### Create Case ### 
**POST /cases**

Request

`POST http://ua-1185-salesforce-system-api.us-e2.cloudhub.io/cases`

Body

```json
[
    {
        "Status": "Working",
        "Origin": "Web",
        "Description": "A case description",
        "Subject": "Case subject",
        "Priority": "High"
    }
]
```
### Create Salesforce Contract ###
**POST /contracts**

Request

`POST http://ua-1185-salesforce-system-api.us-e2.cloudhub.io/contracts`

Response
```json
[
    {
        "AccountId": "001Qy00000OJydlIAD",
        "ExternalId__c": "5eb87ce1ffd86e000604b334",
        "SuccessStatus__c": "1",
        "DateCreation__c": "2024-07-11",
        "Details__c": "Hello",
        "RocketName__c": "Falcon 9",
        "NameSalesforce__c": "Contract1",
        "Status": "Draft",
        "StartDate": "2023-06-26",
        "ContractTerm": 1
    }
]
```
### Get Contract by ID ###
**GET /contracts/{id}**

Request

Request

`GET http://ua-1185-salesforce-system-api.us-e2.cloudhub.io/contracts/5eb87cddffd86e000604b32f`

Response
```json
{
    "Id": "800Qy00000GZAmTIAX",
    "AccountId": "001Qy00000OJydlIAD",
    "ExternalId__c": "23334",
    "SuccessStatus__c": "1",
    "DateCreation__c": "2024-07-11",
    "Details__c": "Hello",
    "RocketName__c": "Rocket",
    "NameSalesforce__c": "Name",
    "Status": "Draft",
    "StartDate": "2023-06-24",
    "ContractTerm": 1
}
```
