---
title: Regulations.gov API
banner-heading: Regulations.gov API
---

<link rel="stylesheet" type="text/css" href="../../assets/swaggerui-dist/swagger-ui.css" >
<link rel="stylesheet" type="text/css" href="../../assets/swaggerui-dist/custom.css" >

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

## OpenAPI Specification File

You can view the full details of this API in the OpenAPI Specification file available here:
<a href="v4/openapi.yaml">Open API specification file for the Sample API</a>

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

## API Calls

{% include swagger-section-header-disable-try-it-out.html %} 
url: "v4/openapi.yaml", 
{% include swagger-section-footer-disable-try-it-out.html %}

<p><small><a href="#">Back to top</a></small></p>


## FAQ

Integer velit ex, sollicitudin sed dolor vitae, consectetur cursus urna. Quisque lacus urna, vulputate non efficitur ut, ornare ac leo. Sed varius, lacus vitae mollis semper, magna lorem pretium erat, non maximus elit justo pretium dolor. Phasellus pellentesque bibendum turpis, eu venenatis eros facilisis sit amet. Pellentesque aliquet dolor ac metus luctus interdum. Vivamus est nibh, blandit non finibus id, tincidunt sed justo. Integer ullamcorper sapien neque, ut lobortis risus interdum ac. Aenean finibus, nibh vitae molestie viverra, nibh mi iaculis lacus, interdum dictum ipsum magna sit amet est. Phasellus vitae faucibus felis. Vivamus non molestie felis, at suscipit lectus. Phasellus ac pulvinar purus, luctus porta elit. Morbi a aliquet tellus. Vivamus mollis, ligula sed egestas euismod, elit lacus auctor dolor, sit amet facilisis purus eros ac augue.

<p><small><a href="#">Back to top</a></small></p>

## Contact Us

Praesent id cursus magna, sodales rutrum mauris. Nulla eget quam at nisl iaculis interdum. In condimentum, mi nec blandit consequat, velit nulla dictum lorem, non scelerisque ex nulla non ex. Sed vitae sem semper, pharetra massa at, vulputate urna. Pellentesque dapibus a ex sit amet pellentesque. Sed eget risus ut felis fringilla ullamcorper vitae a ligula. Aliquam finibus vitae ex sed vehicula.

<p><small><a href="#">Back to top</a></small></p>
