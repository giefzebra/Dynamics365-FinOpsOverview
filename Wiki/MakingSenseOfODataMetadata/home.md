# Introduction
The purpose of this document is to give users an overview to the usage of OData ( https://www.odata.org/ ) and related endpoints within the context of Dynamics 365 Finance & Operations (F&O). I will cover basic concepts within the document, however users may wish to visit the odata.org site for a more detailed explaination of things like what a function means outside of the context of Finance & Operations.

As always, this is my personal interpretation of the system, my background is that of a Dynamics 365 Finance & Operations (formerly 'AX') functional consultant, with a cursory knowledge of the underlying technology. I am **not** an expert in HTTP, REST or OData itself, as a thing, but I am a regular user of these technologies through the lens of F&O

# Endpoints
The Dynamics 365 Finance & Operations platform has an excellent set of endpoints which can be explored by users when considering prototyping external application interactions. The two most common ones are as follows

- Metadata
- Data

## Metadata
This is a descriptive endpoint, which contains information about the data entities within the system, alongside information on labels, which are used in Finance & Operations to enable multilingual support.

The metadata subpoints available are

### Labels
TODO

### Data Entities
This entity contains information about individual entities and is a good starting point for understanding which entities are in the system.
A sample of the data (based on the CustomerV3 entity) returned is illustrated below:

;;;
                {
                    "Name": "CustCustomerV3Entity",
                    "PublicEntityName": "CustomerV3",
                    "PublicCollectionName": "CustomersV3",
                    "LabelId": "@AccountsReceivable:CustCustomerV3EntityLabel",
                    "DataServiceEnabled": true,
                    "DataManagementEnabled": true,
                    "EntityCategory": "Master",
                    "IsReadOnly": false
                }
;;;

This endpoint can be useful primarily for the last 4 elements shown in the sample.

- DataServiceEnabled : The data entity is enabled for odata usage
- DataManagementEnabled : The data entity is enabled for in (bulk) data management, via the client data management functionality and the package API
- EntityCategory: I generally ignore, but can be used for filters if you just want to see master data entities, for example
- IsReadOnly: The data entity is read only, no updates or creates are possible



### Public Entities
TODO

### Public Enumerations
TODO
