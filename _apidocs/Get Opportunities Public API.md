---
title: Get Opportunities Public API documentation
banner-heading: Get Opportunities Public API documentation
---

## Overview

Get Opportunities API provides all the published opportunity details based on the request parameters. This API supports pagination as needed. If pagination is requested, then the response will be provided to users synchronously else the call will be asynchronous. 

## Getting Started

PSC API can be accessed from Beta or Alpha via the following endpoints:
* Beta: <br> 
* Alpha: <br> 

###	Authentication and Authorization

#### Generating a System Account API Key
* Users registered with a government email address and have appropriate System Account Manager or System Account Admin role may request a system account for data access.
* If a user satisfies the above registration criteria they will be able to access the System Accounts widget from their Workspace page after logging in.
* The user can then select “Request System Account” from the widget and fill out the required sections with appropriate Contract Opportunities permissions.
* The requested system account will then need to be approved. After approval the user will be notified via email and they can also see the updated status in the System Account widget.
* The user can select ‘Go to System Accounts’ in the widget from their workspace and enter a new system account password.
* After setting up the password the user will see a new section for retrieving a system account API Key. The user must enter their password again to retrieve the key.


#### System Account Authentication
In order to utilize the Contract Opportunity Management API, the following is required:
* Valid beta.SAM.GOV federal government system account with Read and Write permissions under Contract Opportunity domain.

#### User Account Authorization
In order to perform an Opportunity Management API operation, the following is required:
* beta.SAM.GOV user account with either 'Administrator', 'Contracting Officer' role or 'Contracting Specialist' role. Permissions for operations by role are listed in the table below.<br>

To submit any opportunity notice type (except “Special Notice”) for an office, user should provide Federal Hierarchy (FH) Organization ID or Activity Address Code (AAC) (procurement/non-procurement). To submit Special Notice opportunity, user should provide Federal Hierarchy (FH) Organization ID of office, sub-tier or department or Activity Address Code (AAC) (procurement/non-procurement) or [other codes] for sub-tier and department. 
<br>
<br>
**Note:** Permissions marked "Yes" are may not be assigned by default and will require your user administrator to update.

## Get Opportunities Request Parameters

Users can search by any of the below request parameters with Date field as mandatory. 

Request Parameters that API accepts	| Description | Mandatory?| Data Type
----- | ----- | ----- | -----
api_key	| Public Key of users	| Yes|	String
ptype |	Procurement Type. Below are the available Procurement Types: <br> u= Justification (J&A) <br>p = Pre solicitation <br>a = Award Notice <br>r = Sources Sought <br>s = Special Notice <br>g = Sale of Surplus Property <br>k = Combined Synopsis/Solicitation <br>i = Intent to Bundle Requirements (DoD-Funded) <br><br> Note: Below services are now retired:<br>f = Foreign Government Standard <br>l = Fair Opportunity / Limited Sources  <br> <br>Use Justification (u) instead of fair Opportunity 	|No	|String
solnum|	Solicitation Number|	No|	String
title|	Title|	No	|String
description|	Description|	No|	String
postedFrom	| Posted date From <br>Format must be MM/dd/yyyy <br> Note: Date range between Posted Date From and To is 1 year	|Yes|	String
