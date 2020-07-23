---
title: Regulations.gov API
banner-heading: Regulations.gov API
---

<link rel="stylesheet" type="text/css" href="../../assets/swaggerui-dist/swagger-ui.css" >
<link rel="stylesheet" type="text/css" href="../../assets/swaggerui-dist/custom.css" >

## Overview

When Congress passes laws, federal agencies implement those laws through regulations. These regulations vary in subject, but include everything from ensuring water is safe to drink to setting health care standards. Regulations.gov is the place where users can find and comment on regulations. The APIs allow for users to find creative ways to present regulatory data. To learn more about the program visit the [About Us](https://beta.regulations.gov/about) page.

<p><small><a href="#">Back to top</a></small></p>

## API Description



## Getting Started

To begin using this API, you will need to register for an API Key. You can sign up for an API key here: [API key signup page on api.data.gov](https://api.data.gov/signup/).

After registration, you will need to provide this API key in the `X-Api-Key` HTTP header with every API request.

| HTTP Header Name | Description |
| ---- | ----------- |
| X-Api-Key | API key from api.data.gov.  For sample purposes, you can use `DEMO_KEY` as an API key. |

<p><small><a href="#">Back to top</a></small></p>

## API Description

Regulations.gov offers a GET API for documents, comments, and dockets and a POST API for comments. These endpoints can be used for searching document, comments and dockets, and posting a comment.

#### Searching for documents

You can search for a list of documents based on the criteria passed by using the endpoint https://api.regulations.gov/v4/documents. The search operation supports keyword searches as well as navigation-style searching based on a number of available parameters.

#### Searching for a single document

In order to obtain more details about a single document, you can use the endpoint https:// api.regulations.gov/v4/documents/{documentId}. A document is defined by one of the following types: Proposed Rule, Rule, Supporting & Related, or Other. Each document type has its own set of attributes, which vary based on the Agency posting the document. Another defining characteristic is if the document is part of a Rulemaking or Nonrulemaking Docket.

#### Searching for comments

You can search for a list of comments based on the criteria passed by using the endpoint https://api.regulations.gov/v4/comments. The search operation supports keyword searches as well as navigation-style searching based on a number of available parameters.

#### Searching for a single comment

In order to obtain more details about a single comment, you can use the endpoint https:// api.regulations.gov/v4/comments/{documentId}. Each comment has its own set of attributes, which vary based on the Agency posting the comment. Another defining characteristic is if the comment is part of a Rulemaking or Nonrulemaking Docket.

#### Searching for dockets

A docket is an organizational folder containing multiple documents. Dockets can be searched using the endpoint: https://api.regulations.gov/v4/dockets.

#### Searching for a single docket

In order to obtain more details about a single docket, you can use the endpoint https:// api.regulations.gov/v4/dockets/{docketId}. Each docket has its own set of attributes, which vary based on the Agency posting the docket. Another defining characteristic is if the docket is a Rulemaking or a Nonrulemaking Docket

#### Posting a comment:

User can post a comment using the endpoint https://api.regulations.gov/v4/comments. User can post the comment using one of the following submitter types:

* Individual
* Organization
* Anonymous

If user would like to attach files with their submission, user can get a presigned url for the amazon s3 bucket using the endpoint https://api.regulations.gov/v4/fileUploadUrls

A submissionKey can be retrieved using https://api.regulations.gov/v4/submissionKeys endpoint.

submissionType should be set to API

## OpenAPI Specification File

You can view the full details of this API in the OpenAPI Specification file available here:
<a href="regulationsgov/v4/openapi.yaml">Open API specification file for the Sample API</a>

<p><small><a href="#">Back to top</a></small></p>

## API Calls

{% include swagger-section-header-disable-try-it-out.html %} 
url: "regulationsgov/v4/openapi.yaml", 
{% include swagger-section-footer-disable-try-it-out.html %}

<p><small><a href="#">Back to top</a></small></p>

## Contact Us

If you have any questions or would like to provide feedback, please contact <a href="https://beta.regulations.gov/support">Regulations.gov Help desk</a>.

<p><small><a href="#">Back to top</a></small></p>
