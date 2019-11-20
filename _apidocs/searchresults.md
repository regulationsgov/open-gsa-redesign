---
title: Search.gov Results API
banner-heading: Search.gov Results API
---

## Overview

Search.gov is a service of the General Services Administration, providing search engine capability to federal agencies for their public websites. To learn more about Search.gov and how to set up your site for search, please review the [site launch guide](https://search.gov/manual/site-launch-guide.html).

  This API exposes all relevant Search.gov results “modules” in a single JSON call, including:

  * Web results;
  * Best bets;
  * Health topics;
  * Job openings;
  * Recent tweets;
  * Recent news;
  * Recent video news;
  * Federal Register documents; and
  * Related searches.

  ## Note about Web Results and Endpoints

  The endpoint you use to retrieve web results through this API will depend on the method we used to index your content. If we don't yet have your content indexed, you won't see results in the API.
  
  We can index content using your [XML sitemap](https://search.gov/blog/sitemaps.html) (preferred) or [RSS feeds](#{site_rss_feeds_path(@site)}). We can also deploy a crawler on a limited basis.
  
  Sites indexed via sitemaps or crawling will use the `/search/i14y` endpoint. Because most users are in this category, the example API calls below are to this endpoint. Sites indexed via RSS will use the top level `/search` endpoint, please modify your calls accordingly.

  ## Resource URL

  The endpoint is `https://search.usa.gov/api/v2/search/i14y`.

  You must use https.

  ## Required Parameters

  Three parameters are required: `affiliate`, `access_key`, and `query`.
  `https://search.usa.gov/api/v2/search/i14y?affiliate=YOUR_SITE_HANDLE&access_key=YOUR_UNIQUE_ACCESS_KEY_FROM_ADMIN_CENTER&query=SEARCH_TERM_ENTERED_IN_YOUR_SEARCH_BOX`

  * You can find your access key on the API Access Key page of the Search.gov Admin Center.
  * You can find your site handle on the Settings page.
  * Replace `SEARCH_TERM_ENTERED_IN_YOUR_SEARCH_BOX` with the query entered by the searchers using your website's search box.
  * Preformatted request strings with your unique values are provided in the Admin Center.

  Note that your access key is unique to your site handle so they must be paired properly to return results.

  ## Optional Search Parameters

  All other parameters are optional: `enable_highlighting`, `limit`, `offset`, `sort_by`.

  * ### enable_highlighting

      Enables or disables the highlighting of keywords in the results. The default is 'true' so use 'false' to disable highlighting. The opening and closing highlighting characters are `<U+E000>` and `<U+E001>`, which both look like "". You can learn more about them [here](http://unicodesymbols.wikia.com/wiki/U%2BE000) and [here](http://unicodesymbols.wikia.com/wiki/U%2BE001) (external resources). Your team will determine how to display the characters, whether as bold, italics, or some other preferred highlighting style.
     `https://search.usa.gov/api/v2/search/i14y?affiliate=YOUR_SITE_HANDLE&access_key=YOUR_UNIQUE_ACCESS_KEY_FROM_ADMIN_CENTER&query=SEARCH_TERM_ENTERED_IN_YOUR_SEARCH_BOX&enable_highlighting=false`

  * ### limit

      Defines the number of results to return. The default is 20, but you can specify between 1 and 50 results.
   `https://search.usa.gov/api/v2/search/i14y?affiliate=YOUR_SITE_HANDLE&access_key=YOUR_UNIQUE_ACCESS_KEY_FROM_ADMIN_CENTER&query=SEARCH_TERM_ENTERED_IN_YOUR_SEARCH_BOX&limit=5`

  * ### offset

      Defines the number of results you want to skip from the first result. The default is 0 and the maximum is 999.
      `https://search.usa.gov/api/v2/search/i14y?affiliate=YOUR_SITE_HANDLE&access_key=YOUR_UNIQUE_ACCESS_KEY_FROM_ADMIN_CENTER&query=SEARCH_TERM_ENTERED_IN_YOUR_SEARCH_BOX&offset=20`

  * ### sort_by

      Sort the results by date. The default is sort by relevance.
      `https://search.usa.gov/api/v2/search/i14y?affiliate=YOUR_SITE_HANDLE&access_key=YOUR_UNIQUE_ACCESS_KEY_FROM_ADMIN_CENTER&query=SEARCH_TERM_ENTERED_IN_YOUR_SEARCH_BOX&sort_by=date`

  ## Response Fields

  Each item returns a unique set of fields.

  * ### web:results

      Web results from our Search.gov indexes.

      | Values           | Description
      | :--              | :--
      | title            | Title of the document
      | url              | URL of the document
      | snippet          | Summary of the document
      | publication_date | Publication date of the document (not available on commercial results)

  * ### web:total

      Total number of results available.

  * ### web:next_offset

      Offset for the subsequent results.

  * ### web:spelling_correction

    Spelling correction for your search term.

  * ### text_best_bets

      Text best bets, which appear only when the query matches the text of the best bet’s title, description, or keywords.

      | Values      | Description
      | :--         | :--
      | title       | Title of the best bet
      | url         | URL of the best bet
      | description | Description of the best bet

  * ### graphic_best_bets

      Graphic best bets, which appear only when the query matches the text of the best bet’s title, description, or keywords.

      | Values         | Description
      | :--            | :--
      | title          | Title of the graphic best bet
      | title_url      | URL of the graphic best bet
      | image_url      | URL of the graphic image
      | image_alt_text | Alternative text of the image
      | links          | An array of links in the graphic best bet. Each link contains a title and a URL

  * ### health_topics

      | Values         | Description
      | :--            | :--
      | title          | Title of the health topic
      | url            | URL of the health topic
      | snippet        | Snippet of the health topic
      | related_topics | An array of topics related to the health topic. Each topic contains a title and a URL
      | related_sites  | An array of sites related to the the health topic. Each site contains a title and a URL

  * ### job_openings

      | Values             | Description
      | :--                | :--
      | position_title     | Position title of the job opening
      | organization_name  | Organization name of the job opening
      | rate_interval_code | Rate interval code of the job opening
      | minimum            | Minimum salary of the job opening
      | maximum            | Maximum salary of the job opening
      | start_date         | Start date of the job opening
      | end_date           | End date of the job opening
      | locations          | An array of locations of the job opening
      | url                | URL of the job opening

  * ### recent_tweets

      | Values            | Description
      | :--               | :--
      | text              | Text of the tweet
      | url               | URL of the tweet
      | name              | Name of the tweet author
      | screen_name       | Screen name of the tweet author
      | profile_image_url | URL of the tweet author profile image

  * ### recent_news

      Recent news from our Search.gov indexes. Only available with commercial results.

      | Values           | Description
      | :--              | :--
      | title            | Title of the recent news
      | url              | URL of the recent news
      | snippet          | Snippet of the recent news
      | publication_date | Publication date of the recent news
      | source           | Source of the recent news

  * ### recent_video_news

      Recent video news from our Search.gov indexes. Only available with commercial results.

      | Values           | Description
      | :--              | :--
      | title            | Title of the recent video news
      | url              | URL of the recent video news
      | snippet          | Snippet of the recent video news
      | publication_date | Publication date of the recent video news
      | source           | Source of the recent video news
      | thumbnail_url    | Thumbnail URL of the recent video news

  * ### federal_register_documents

      Federal Register documents

      | Values              | Description
      | :--                 | :--
      | id                  | The ID of the document as known to usasearch
      | document_number     | Document number of the federal register document
      | document_type       | Document type of the federal register document
      | title               | Title of the federal register document
      | url                 | URL of the federal register document
      | agency_names        | An array of agency names of the federal register document
      | page_length         | Page length of the federal register document
      | start_page          | Start page of the federal register document
      | end_page            | End page of the federal register document
      | publication_date    | Publication date of the federal register document
      | comments_close_date | Comments close date of the federal register document

  * ### related_search_terms

      An array of related search terms, which are based on recent, common searches on the your site.

<p><small><a href="#">Back to top</a></small></p>

## Getting Started

To begin using this API, you will need to register for an API Key. You can sign up for an API key here: [API key signup page on api.data.gov](https://api.data.gov/signup/).

After registration, you will need to provide this API key in the `x-api-key` HTTP header with every API request.

| HTTP Header Name | Description |
| ---- | ----------- |
| x-api-key | API key from api.data.gov.  For sample purposes, you can use `DEMO_KEY` as an API key. |




<p><small><a href="#">Back to top</a></small></p>

## API Description



This API has two primary endpoints:

**Endpoint 1:** https://api.gsa.gov/travel/citypairs/v0/airfares

**Description**   Negotiated airfares

**Query String Parameters**

| Parameter Name | Description |
| ---- | ----------- |
| award_year string | Year of airfare award. Example: '2017' |
| origin_airport_abbrev string | Origin airport abbreviation. Example: 'ABQ'. Must include either this or the destination airport abbreviation. |
| destination_airport_abbrev | Destination airport abbreviation. Example: 'BWI'. Must include either this or the origination airport abbreviation. |

**Expected Result**

| Name  | Description |
| ---- | ----------- |
| ID (integer, optional) | Generated unique identifier. |
| ITEM_NUM (string, optional) | Item number. |
| AWARD_YEAR (string, optional) | Award Year. |
| ORIGIN_AIRPORT_ABBREV (string, optional) | Origin Airport Abbreviation. |
| DESTINATION_AIRPORT_ABBREV (string, optional) | Destinatoin Airport Abbreviation. |
| ORIGIN_CITY_NAME (string, optional) | Original City Name. |
| ORIGIN_STATE (string, optional) | Origin State. |
| ORIGIN_COUNTRY (string, optional) | Origin Country. |
| DESTINATION_CITY_NAME (string, optional) | Destination City Name. |
| DESTINATION_STATE (string, optional) | Destination State. |
| DESTINATION_COUNTRY (string, optional) | Destination Country. |
| AIRLINE_ABBREV (string, optional) | Airline Abbreviation. |
| AWARDED_SERV (string, optional) | Awarded Serv. |
| PAX_COUNT (string, optional) | PAX Count. |
| YCA_FARE (integer, optional) | YCA Fare. |
| XCA_FARE (integer, optional) | XCA Fare. |
| BUSINESS_FARE (integer, optional) | Business Fare. |
| ORIGIN_AIRPORT_LOCATION (string, optional) | Origin Airport Location. |
| DESTINATION_AIRPORT_LOCATION (string, optional) | Destination Airport Location. |
| ORIGIN_CITY_STATE_AIRPORT (string, optional) | Origin City State Airport. |
| DESTINATION_CITY_STATE_AIRPORT (string, optional) | Destination City State Airport. |
| EFFECTIVE_DATE (string, optional) | Expiration Date. |
| EXPIRATION_DATE (string, optional) | Expiration Date. |



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

