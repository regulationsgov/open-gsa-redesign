---
title: Regulations.gov API
banner-heading: Regulations.gov API
---


## Overview

When Congress passes laws, federal agencies implement those laws through regulations. These regulations vary in subject, but include everything from ensuring water is safe to drink to setting health care standards. Regulations.gov is the place where users can find and comment on regulations. The APIs allow for users to find creative ways to present regulatory data. To learn more about the program visit the [About Us](https://beta.regulations.gov/about) page.

<p><small><a href="#">Back to top</a></small></p>

## Getting Started

To begin using this API, you will need to register for an API Key. You can sign up for an API key here: [API key signup page on api.data.gov](https://api.data.gov/signup/).

After registration, you will need to provide this API key in the `x-api-key` HTTP header with every API request.

| HTTP Header Name | Description |
| ---- | ----------- |
| x-api-key | API key from api.data.gov.  For sample purposes, you can use `DEMO_KEY` as an API key. |




<p><small><a href="#">Back to top</a></small></p>

## API Description



This API has three primary endpoints:

** Documents:** https://api.gsa.gov/regulationsgov/v4/documents/

**Description**   Document Requests

**Query String Parameters**

| Action | Parameter| Description |
|---|---|---|
| filter | agencyId	| Filters results for the agency acronym specified in the value. |
|| commentEndDate | Filters results relative to the comment end date.  The value must be formatted as `MM-dd-yyyy`.<br/><br/> Omission of a parameter modifier will match results to the exact date provided, otherwise, one of the parameter modifiers below may be used: <br/> `ge` - greater than or equal <br/> `le` - less than or equal |
|| docketId | Filters results on the specified docket ID. |
|| documentType | Filters results on the specified document type. |
|| searchTerm | Filters results on the given term. |
|| postedDate | Filters results relative to the posted date.  The value must be formatted as `MM-dd-yyyy`.<br/><br/> Omission of a parameter modifier will match results to the exact date provided, otherwise, one of the parameter modifiers below may be used: <br/> `ge` - greater than or equal <br/> `le` - less than or equal |
|| subtype | Filters results on the supplied document subtype |
|| withinCommentPeriod | Filters results for documents that are open for comment by setting the value to `true`. <br/><br/> _`False` is not an acceptable value for this parameter, hence it should be removed when not being used._ |
| sort | (none) | Sorts the results on the field specified in the value.  The default behavior will sort the results in ascending order; to sort in descending order, prepend a minus sign to the value. <br/><br/> Supported values are `commentEndDate`, `postedDate`, and `title`. |
| page | number | Specifies the number for the page of results that will be returned from the query. <br/><br/> Acceptable values are numerical between, and including, 1 and 20. |
|| size | Specifies the size per page of results that will be returned from the query. <br/><br/> Acceptable values are numerical between, and including, 5 and 250. |

Complex queries can be made by combining multiple actions and/or parameters.  However, only one sort will be applied and a page number and size should each only be provided once per query.

**Documents Response**

| Property | Type | Description |
| --- | --- | --- |
| additionalRins | Collection of Strings | One or more Regulatory Information Numbers (RINs) to which the document relates. |
| address1 | String | The first line of the submitter's address. |
| address2 | String | The second line of the submitter's address. |
| agencyId | String | The acronym used to abbreviate the name of the agency associated with the document. |
| allowLateComments | Boolean | Indicates whether the owning agency will accept comments on the document after the due date. |
| attachments | Collection of Objects | See <a href="#document_attachments">Attachments</a> for further details. |
| authorDate | String | The date that the authors wrote or published the document.<br/><br/>The date is formatted as ISO 8601 with an offset such as `2019-01-20T13:15:45+01:00`. |
| authors | Collection of Strings | The individual, organization, or group of collaborators that contributed to the creation of the document. |
| cfrPart | String | The Code of Federal Regulations (CFR) Citation applicable to the document. |
| city | String | The city associated with the submitter's address. |
| comment | String | The body of a submitted comment. |
| commentCategory | String | An agency-specific category allowing agencies to group comments according to their type. |
| commentEndDate | String | The date that closes the period when public comments may be submitted on the document.<br/><br/>The date is formatted as ISO 8601 with an offset such as `2019-01-20T13:15:45+01:00`. |
| commentOn | String | The unique Regulations.gov ID of the document on which the comment has been made.  This value is often expected for internal use only.  |
| commentOnDocumentId | String | The ID of the document on which the comment has been made. |
| commentStartDate | String | The date that begins the period when public comments may be submitted on the document.<br/><br/>The date is formatted as ISO 8601 with an offset such as `2019-01-20T13:15:45+01:00`. |
| content | String | The content of a document that has originated from the [Federal Register](https://www.federalregister.gov/). |
| country | String | The country associated with the submitter's address. |
| displayProperties | Collection of Objects | See <a href="#display_properties">Display Properties</a> for further details. |
| docAbstract | String | The detailed description of the document. |
| docketId | String | The ID of the docket to which the document corresponds. |
| documentType | String | The document type.<br/><br/>Possible values are `Notice`, `Rule`, `Proposed Rule`, `Supporting & Related Material`, `Public Submission`, and `Other`. |
| duplicateComments | Integer | The number of duplicate or significantly similar comments made on the associated document. |
| effectiveDate | String | The date the document is put into effect.<br/><br/>The date is formatted as ISO 8601 with an offset such as `2019-01-20T13:15:45+01:00`. |
| email | String | The submitter's e-mail address. |
| exhibitLocation | String | The physical location of an exhibit to which a document refers. |
| exhibitType | String | The type of exhibit to which a document refers. |
| fax | String | The submitter's fax number. |
| field1 | String | An agency-specific field used for storing additional data with the document. |
| field2 | String | An agency-specific field used for storing additional data with the document. |
| fileFormats | Collection of Objects | See <a href="#document_file_formats">File Formats</a> for further details. |
| firstName | String | The submitter's first name. |
| frDocNum | String | The unique identifier of a document originating in the [Federal Register](https://www.federalregister.gov/). |
| frVolNum | String | The [Federal Register](https://www.federalregister.gov/) volume number where the document was published. |
| govAgency | String | The name of the government agency that the submitter represents. |
| govAgencyType | String | The type of government agency that the submitter represents. |
| objectId | String | The unique Regulations.gov ID associated with the document.  This value is often expected for internal use only. |
| implementationDate | String | The date the document is to be implemented.<br/><br/>The date is formatted as ISO 8601 with an offset such as `2019-01-20T13:15:45+01:00`. |
| lastName | String | The submitter's last name.  |
| legacyId | String | An agency-specific identifier that was given to the document in the legacy system. |
| media | String | The media in which the document is stored. |
| modifyDate | String | The date when the document was last modified.<br/><br/>The date is formatted as ISO 8601 with an offset such as `2019-01-20T13:15:45+01:00`. |
| ombApproval | String | The control number assigned when approval is given by the Office of Management and Budget (OMB) in accordance with the Paperwork Reduction Act (PRA).  |
| organization | String | The organization that the submitter represents. |
| originalDocumentId | String | The document ID that was assigned when first entered into the system should a change occur that requires a new document ID to be assigned. |
| pageCount | Integer | Conveys the number of pages contained in the document. |
| paperLength | Integer | When the document is in paper format, indicates the length of the paper. |
| paperWidth | Integer | When the document is in paper format, indicates the width of the paper. |
| phone | String | The submitter's phone number. |
| postedDate | String | The date that the document was posted by the agency to the system.<br/><br/>The date is formatted as ISO 8601 with an offset such as `2019-01-20T13:15:45+01:00`. |
| postmarkDate | String | The postmark date of a document that was sent by mail.<br/><br/>The date is formatted as ISO 8601 with an offset such as `2019-01-20T13:15:45+01:00`. |
| reasonWithdrawn | String | If the document is withdrawn, this field will state the reason. |
| receiveDate | String | The date that the agency received or created the document.<br/><br/>The date is formatted as ISO 8601 with an offset such as `2019-01-20T13:15:45+01:00`. |
| regWriterInstruction | String | Additional instructions provided by the writer of the regulation. |
| restrictReason | String | Additional information about the restriction of a document when the `restrictReasonType` is `Other`. |
| restrictReasonType | String | Indicates the type of restriction placed on the document.  For the type, `Other`, additional information can be found with the `restrictReason`. |
| sourceCitation | String | The citation for the source that published the document. |
| startEndPage | String | The starting and ending pages where the document was published. |
| stateProvince | String | The state or province of the submitter's address. |
| subject | String | The subject of the document. |
| submitterRep | String | The name of the representative that has made a submission on behalf of the submitter. |
| submitterRepAddress | String | The submitter representative's address. |
| submitterRepCityState | String | The city and state associated with the submitter representative's location. |
| subtype | String | An agency-specific attribute to further categorize a document beyond the type (`documentType`). |
| title | String | The formal title of the document. |
| topics | Collection of Strings | The principal topics to which the document pertains. |
| trackingNbr | String | The identifier assigned to the document that may be used to track its lifecycle within the system and is often used when interacting with the help desk. |
| withdrawn | Boolean | Conveys if the document is withdrawn. |
| zip | String | The zip code associated with the submitter's address. |
| openForComment | Boolean | Indicates if the current date is between the comment start date and comment end date.  If the value is `true`, comments are being accepted for the document. |



**Endpoint 2:** https://api.gsa.gov/travel/citypairs/v0/airfares/{id}

**Description**   Individual airfare by ID

**Query String Parameters**

| Parameter Name | Description |
| ---- | ----------- |
| id integer | Unique Identifier |

**Expected Result**
(Same response as endpoint 1)

<p><small><a href="#">Back to top</a></small></p>

## OpenAPI Specification File

You can view the full details of this API in the OpenAPI Specification file available here:
<a href="v1/openapi.yaml">Open API specification file for the Sample API</a>

<p><small><a href="#">Back to top</a></small></p>

## HTTP Response Codes

The API will return one of the following responses:

| HTTP Response Code | Description |
| ---- | ----------- |
| 200 | Successful. Data will be returned in JSON format. |
| 400 | Bad request. Verify the query string parmaters that were provided. |
| 403 | API key is not correct or was not provided. |
| 4XX | Additional 400-level are caused by some type of error in the information submitted. |

<p><small><a href="#">Back to top</a></small></p>


## FAQ

Integer velit ex, sollicitudin sed dolor vitae, consectetur cursus urna. Quisque lacus urna, vulputate non efficitur ut, ornare ac leo. Sed varius, lacus vitae mollis semper, magna lorem pretium erat, non maximus elit justo pretium dolor. Phasellus pellentesque bibendum turpis, eu venenatis eros facilisis sit amet. Pellentesque aliquet dolor ac metus luctus interdum. Vivamus est nibh, blandit non finibus id, tincidunt sed justo. Integer ullamcorper sapien neque, ut lobortis risus interdum ac. Aenean finibus, nibh vitae molestie viverra, nibh mi iaculis lacus, interdum dictum ipsum magna sit amet est. Phasellus vitae faucibus felis. Vivamus non molestie felis, at suscipit lectus. Phasellus ac pulvinar purus, luctus porta elit. Morbi a aliquet tellus. Vivamus mollis, ligula sed egestas euismod, elit lacus auctor dolor, sit amet facilisis purus eros ac augue.

<p><small><a href="#">Back to top</a></small></p>

## Contact Us

Praesent id cursus magna, sodales rutrum mauris. Nulla eget quam at nisl iaculis interdum. In condimentum, mi nec blandit consequat, velit nulla dictum lorem, non scelerisque ex nulla non ex. Sed vitae sem semper, pharetra massa at, vulputate urna. Pellentesque dapibus a ex sit amet pellentesque. Sed eget risus ut felis fringilla ullamcorper vitae a ligula. Aliquam finibus vitae ex sed vehicula.

<p><small><a href="#">Back to top</a></small></p>
