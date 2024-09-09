<a href="https://softserve.academy/"><img src="https://s.057.ua/section/newsInternalIcon/upload/images/news/icon/000/050/792/vnutr_5ce4f980ef15f.jpg" title="SoftServe IT Academy" alt="SoftServe IT Academy"></a>


## Installation

- All the `code` required to get started
- Images of what it should look like

### Required to install
* Java 21.0.3
* Apache Maven 3.9.6
* Anypoint Studio 7.17


### Environment

Global variables and sample filling


```properties

-M-Ddogkey=*******
-M-Ddoghost=datadoghq.eu
-M-DAZURE_CLIENT_ID=*****-*****-4a19-9845-b0d85c8fbfd5
-M-DAZURE_TENANT_ID=***-***-4127-8255-d2019c39f914
-M-DAZURE_CLIENT_SECRET=*****~*******O0~BLvpV7kEJ8lxyRdkoaN4 
-M-DMULE_AZURE_KEY_VAULT_NAME=mulesoft1185
-M-DFREQUENCY=1
```

### Clone

- Clone this repo to your local machine using `https://github.com/BelousSofiya/general-project.git`

### Open Anypoint Studio and import project

- For all the possible languages that support syntax highlithing on GitHub (which is basically all of them), refer <a href="https://github.com/github/linguist/blob/master/lib/linguist/languages.yml" target="_blank">here</a>.

### Run the project

## Team

> Or Contributors/People

- Bilous Sofiya
- Maliarenko Sofiya
- Malikova Alina
- Pavlenko Igor
- Kuhar Igor
- Mykolyshyn Roman
- Karavaieva Anastasiia
- Holyboroda Serhii

---

## Task. General concept

General concept

SpaceX API is a reliable source of data for us. We need to implement a process for synchronizing certain sets of data from SpaceX API into our databases. 
These processes must be reliable, well-logged, and run once using different methods. 
On the other hand, we need a mechanism that ensures random changes in data in our databases. For this purpose, endpoints based on randomness should be developed. 
Moreover, there is also the Salesforce side, which will contain information about Contracts (Launches in our databases) and Cases. 
When changing the Contract in Salesforce, the corresponding Launch in the databases must be changed. And when synchronization starts, the databases and Salesforce should be updated with data from SpaceX.

Expected output:
  - SpaceX-Process-API + repo
  - SpaceX-System-API + repo
  - MySQL-System-API + repo
  - MongoDB-System-API + repo
  - Salesforce-System-API + repo
  - common-project + repo
  - 1 MySQL/Mongo account
  - 1 Salesforce account
  - 1 DataDog account
  - 1 Azure Key Vault account
  - 1 ActiveMQ account
  - 2 email accounts
  - 1 Anypoint Platform account
  

#### Anastasiia Karavaieva
Unite 2 MySQL applications into 1, prepare 1 WSDL.
Implement Creation, Updating and Deleting operations for Launches, LaunchPads, Rockets and Payloads. 
Deploy the application and apply White list policy just for SpaceX-Process-API application IP. Here you should work according to externalId.

#### Igоr Kukhar
Unite 2 Mongo DB applications into 1, prepare WSDL.
Implement Creation, Updating and Deleting operations for Launches, LaunchPads, Rockets and Payloads. Here you should work according to externalId.
Deploy the application and apply White list policy just for SpaceX-Process-API application IP.


#### Sofiya Maliarenko
Unite 4 SpaceX applications into 1, prepare RAML. RAML must be connected from Design Center.
Create trial account of Salesforce. Share credentials with the team.
Create REST Salesforce-System-API and implement 1 endpoint for Case creation and 2 endpoints for creation/updating of Contract (See Mapping).
Deploy the application and apply White list policy just for SpaceX-Process-API application IP.

#### Roman Mykolyshyn
Create and configurate DataDog account. Share credentials with the team.
Create Azure Key Vault account. Share credentials with the team.
Create email account for error notifications ua.1185.si.mulesoft.support@gmail.com, share credentials.
Create email account for reports ua.1185.si.mulesoft.report@gmail.com, share credentials.
Create and implement common-project which will be included in each application as dependency.
Implement error handler strategy for handling all errors from all applications.
Add loggers for each error scope following defined format (See Log message examples).
If an error appears on system layer - the error must be handled on system and process layers.
If an error appears, Salesforce Case (See Mapping) must be created and email notification must be sent (Mail content with error info, Title).

#### Sofiya Bilous
Create and implement business flow which listens to the updates of Salesforce Contract and updates Launch data in MySQL and Mongo DB (See Mapping).
The flow must be triggered with On New/On Modified Contract.

#### Alina Malikova
Create and implement business flow for sync LaunchPads, Rockets and Payloads data without pagination.
At the end of the flow a report file must be created and sent (See Report example).
The flow must be available by HTTPS protocol.
The flow must work in two modes: working and safety.
Working mode - the data must be applied in DBs (hard change).
Safety mode - the report must be created but without updating data in DBs.
The flow must query all data for all SpaceX entities (from SpaceX-System-API), check difference between SpaceX and DBs and create/update records/docs in DBs if it needed.
The report must be sent to ua.1185.si.mulesoft.report@gmail.com (See Report example).

#### Serhii Holyboroda
Create and implement business flow for sync Launches.
At the end of the flow a report file must be created and sent (See Report example).
The flow must be triggered with Active MQ message (P-to-P for example).
Pagination strategy must be implemented for the flow and for each Launch on the page requests to MySQL, Mongo DB and Salesforce must be executed.
In case in difference found - add info to report and create/update in DBs.
The flow must work in two modes: working and safety.
Working mode - the data must be applied in DBs (hard change).
Safety mode - the report must be created but without updating data in DBs.
Preffered tools: VM Queue, Object Store, Batch

#### Igor Pavlenko
Create and implement business flow which will be available by HTTPS protocol.
The main purpose of the flow is Updating and Deleting rows and columns in MySQL and Mongo DB.
The flow must work with Launches, LaunchPads, Rockets and Payloads.
For each entity, a record for deleting is randomly selected, with a certain chance. 
Based on the remaining records, a field for updating is randomly selected, also with a certain chance. 
For string data, you can use concatenation with a string literal. 
For date, you can change the date by adding a few days or weeks. 
The same is true for numeric data. 
The data needs to be updated and deleted both in MySQL and in Mongo DB for all entities and starting the process 1 time. 
Try to have as much randomness and flexibility as possible. 
All random parameters should be in property files and can be easily changed. 
Unchanged records should also remain, approximately 50/50. 
The number of changed and deleted records for each entity should be logged.


#### Common tasks:
- You should use 1 common trial Anypoint Platform account for all your RAMLs and deployed apps.
- All RAMLs must be in Design Center with all required types, examples, traits etc.
- All WSDLs must be created with all required schemes, types etc.
- All business flows must be implemented inside new SpaceX-Process-API application. The app must work with target systems across system layer applications only. 
- Property files should not contain any sensitive info (username/pass) except of credentials for Azure Key Vault. These creds must be encrypted. Other properties must be decrypted.
- Credentials for MySQL, MongoDB, Salesforce, Active MQ must be in Azure Key Vault system.
- Each application must contain: ua-1185-{spacex/mysql/mongodb/salesforce}-{process/system}-api.xml, ua-1185-{spacex/mysql/mongodb/salesforce}-{process/system}-impl.xml, ua-1185-{spacex/mysql/mongodb/salesforce}-{process/system}-config.xml files
- Each business flow must contain loggers, not too much. You should log just important steps (receive/send info, end of large step, all errors(for common-project)).
- Each log should follow standard format(see Log message examples).
- Each log must be written in CloudHub and DataDog system. DataDog system will be 1 for all applications. Log4j file must be modified (see DataDog Mule appender) for this purpose.
- All applications must use 1 global error handler, which is located in common-project.
- MUnit coverage must not be less than 70%. Common-project and error handler can be excluded from the coverage.




Mapping:

           SpaceX API           MySQL              Mongo DB           Salesforce

Launch:                                  
           id                   externalId         externalId         {need to be created as a custom field}
           -                    -                  docType            -
           name                 launchName         launchName         Name
           success              success            success            {need to be created as a custom field}
           details              details            details            {need to be created as a custom field}
           date_utc             date               date               EndDate
           roket(id)->name      rocketName         rocketName         {need to be created as a custom field}

LaunchPad
           id                   externalId         externalId         -
           -                    -                  docType            -
           name                 name               name               -
           locality             locality           locality           -
           region               region             region             -
           status               status             status             -

Rocket
           id                   externalId         externalId         -
           -                    -                  docType            - 
           name                 name               name               -
           active               active             active             -
           stages               stages             stages             -
           cost_per_launch      costPerLaunch      costPerLaunch      -
           description          description        description        -

Payload
           id                   externalId         externalId         -
           -                    -                  docType            -
           name                 name               name               -
           type                 type               type               -
           mass_kg              weight             weight             -
           orbit                orbit              orbit              -
           apoapsis_km          apoapsis           apoapsis           -
           periapsis_km         periapsis          periapsis          -

Case
           -                    -                  -                  Description
           -                    -                  -                  Subject
           -                    -                  -                  CreatedDate
           -                    -                  -                  Priority




Report example:

Start report

- Source: MySQL/MongoDB
- Mode: WORKING/SAFETY
- DateTime: 14-06-2024 20:32:12
- Requestor: ActiveMQ/Direct HTTPS

Content
------------------------------------------------------------------------

LaunchPads:
  - 2143457655674554 name: {old_name} -> {new_name}, locality: {old_locality} -> {new_locality}, ...
  - 2345324532453234 name, locality, {docType}, status, region CREATED

Rockets:
  2134214321421343 -//- -//-
  -//-
  -//-
-//-

End report

If no records for updating/adding - no records for report.
The name of report file must be in format 14-06-2024-{https/activemq}-sync-report.txt


Log message examples:
   - SUCCESS: SpaceX-System-API response contains 10 rows (Launches)
   - SUCCESS: Rocket with externalId '123421345564' was updated in MySQL
   - SUCCESS: Payload with externalId '2141234123423' was added in MongoDB
   - SUCCESS: Synchronization event for LaunchPads, Rockets and Payloads was received. This is SAFETY mode.
   - SUCCESS: Synchronization process was run...
   - SUCCESS: Synchronization process was finished
   - ERROR: Error was received during creation process for new Launch. Launch externalId: '12412424'. Error details: {error details as string}

Links:
   - DataDog: https://www.datadoghq.com/
   - DataDog Mule appender: https://docs.mulesoft.com/cloudhub/custom-log-appender
   - Azure Key Vault Connector: https://docs.mulesoft.com/azure-key-vault-connector/latest/azure-key-vault-connector-examples
   - Azure Key Vault Guide: https://www.youtube.com/watch?v=A8dJL43zDYA
   - Salesforce Account: https://www.salesforce.com/in/form/signup/freetrial-sales/
   - Active MQ Guide: https://www.youtube.com/watch?v=5fUXO0YkYEI&list=PL5GwZHHgKcuCtFA-0ZRVgdGPQozwZ-nJu
   - HTTPS in Mule: https://medium.com/@gursimransingh1298/implementing-one-way-ssl-for-mulesoft-applications-3173aa4965f2

Tips:

Those who work on system level applications - try to prepare RAML/WSDL as soon as possible so that you do not block those who work on the process level and use your interfaces.

---



## License

[![License](http://img.shields.io/:license-mit-blue.svg?style=flat-square)](http://badges.mit-license.org)

- **[MIT license](http://opensource.org/licenses/mit-license.php)**
- Copyright 2020 © <a href="https://softserve.academy/" target="_blank"> SoftServe IT Academy</a>.