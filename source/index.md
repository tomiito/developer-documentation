---
title: Fulcrum API Documentation

language_tabs:
  - shell : curl
  - ruby : Ruby
  - php : PHP
  - python : Python
  - csharp : C#
  - javascript : Node.js

toc_footers:
  - <a href='https://luc.id/fulcrum/'>Get access to Fulcrum APIs</a>

includes:
  - errors
  
search: true
---
# Introduction

> API Endpoint:

```plaintext
https://stg-api.samplicio.us/
```

Lucid brings efficiency and automation to online sampling with Fulcrum, today’s most powerful, open, and customizable online sampling platform.
    
The API is based on REST (REpresentational State Transfer) principles, which makes it very easy to write and test applications. Both JSON and XML data formats are supported.

# Guides

# Authentication

# Resources

To begin testing the Fulcrum API, first download a REST Client extension for your browser. Whether you are testing the Supply or Demand API, you will need a REST Client in order to make POST, PUT,     and DELETE calls. All GET calls can be made directly through your browser.

* Chrome Simple REST Client: <https://chrome.google.com/webstore/detail/simple-rest-client/fhjcajmcbmldlhcimfajhfbgofnpcjmb>
* Chrome Postman REST Client: <https://chrome.google.com/webstore/detail/postman-rest-client/fdmmgilgnpjigdojojpjoooidkmcomcm?hl=en>
* Firefox RESTClient: <https://addons.mozilla.org/en-US/firefox/addon/restclient/>
* Opera Simple REST Client: <https://addons.opera.com/en/extensions/details/simple-rest-client/?display=en>

# Environments

# Interacting with the API

## Making an API Call

All Example Call pages on this site contain a base Staging URL. This URL can be used along with the [Generic Staging API Key](http://developer.fulcrumexchange.com/?p=327) to make test calls to the Fulcrum API; any parameters listed in [brackets] should also be replaced. For example, appending the Fulcrum SurveyNumber and the Generic Staging API Key to the GET call below will allow you to make a call directly in your browser’s address bar.

### Base URL

`GET  http://stg-api.samplicio.us/Demand/v1/Surveys/BySurveyNumber/[SurveyNumber]?key=[APIKey]`

### Example URL

`GET  http://stg-api.samplicio.us/Demand/v1/Surveys/BySurveyNumber/22789?key=5175285E-D74B-46A8-AE2C-EF95B3A5175B`

## JSON versus XML

The Fulcrum API requires by default that all requests and responses be written in JSON, but developers who prefer XML can use that language, as well. To turn any JSON call into an XML call, simply append “/xml” to any Request URL immediately before appending any request parameters or the API key.

### JSON URL

`GET  http://stg-api.samplicio.us/Demand/v1/Surveys/BySurveyNumber/22789?key=5175285E-D74B-46A8-AE2C-EF95B3A5175B`

### XML URL

`GET  http://stg-api.samplicio.us/Demand/v1/Surveys/BySurveyNumber/xml/22789?key=5175285E-D74B-46A8-AE2C-EF95B3A5175B`

# HTTP Status Codes

# Changelog

# Lookup

# Definitions

##List Global Definitions

##List Suppliers

##List Business Units

#Question Library

##List Standard Qualifications

##List Custom Qualifications

##Show Question Text

##Show Question Options

# Supply

# Surveys

##List Exchange Surveys

> Definition

```plaintext
GET  https://api.samplicio.us/Supply/v1/Surveys/AllOfferwall/{SupplierCode}?key={APIKey}
```

> Example Request

```shell
curl https://api.samplicio.us/Supply/v1/Surveys/AllOfferwall/{SupplierCode}?key={APIKey}
```

```ruby
require 'open-uri'

open('https://api.samplicio.us/Supply/v1/Surveys/AllOfferwall/{SupplierCode}?key={APIKey}')
```

```php
file_get_contents('https://api.samplicio.us/Supply/v1/Surveys/AllOfferwall/{SupplierCode}?key={APIKey}');
```

```python
from urllib2 import urlopen

urlopen('https://api.samplicio.us/Supply/v1/Surveys/AllOfferwall/{SupplierCode}?key={APIKey}')
```

```csharp
using System.Net;

(HttpWebRequest)WebRequest.Create("https://api.samplicio.us/Supply/v1/Surveys/AllOfferwall/{SupplierCode}?key={APIKey}");
```

```javascript
var xhr = new XMLHttpRequest();
xhr.open("GET", "https://api.samplicio.us/Supply/v1/Surveys/AllOfferwall/{SupplierCode}?key={APIKey}", true);
xhr.send();
```

> Example Response

```json 
{
  "ApiResult": 0,
  "ApiResultCode": 0,
  "ApiAccount": "Anon",
  "AccountType": 2,
  "ApiAccountStatus": 1,
  "AccountCode": "AA",
  "ApiMessages": [
    "API Message: Response initialized.",
    "API Message: GetAllOfferwallSurveys successful."
  ],
  "ResultCount": 3,
  "Surveys": [
    {
      "SurveyName": "Asthma Sufferers",
      "SurveyNumber": 457751,
      "SurveySID": "26CB55E2-74CC-4E19-88E3-7F2F8D4DE74D",
      "AccountName": "Sample Company",
      "CountryLanguageID": 9,
      "LengthOfInterview": 12,
      "BidIncidence": 30,
      "Conversion": 1,
      "CPI": 1.5,
      "FieldEndDate": "\/Date(1388293200000-0600)\/",
      "IndustryID": 30,
      "StudyTypeID": 1,
      "OverallCompletes": 5,
      "TotalRemaining": 995,
      "CompletionPercentage": 0,
      "SurveyGroup": null,
      "SurveyGroupID": null,
      "SurveyGroupExists": 1,
      "BidLengthOfInterview": 10,
      "TerminationLengthOfInterview": 6,
      "SurveyQuotaCalcTypeID": 1,
      "IsTrueSample": false,
      "SurveyMobileConversion": 0,
      "SampleTypeID": null
    },
    {...},
    {...}
  ]
}
```

##List Allocated Surveys

##Show an Allocated Survey

##List Updated Allocated Surveys

##List a Survey’s Groups

#Qualifications

##Show Qualifications

#Quotas

##Show Quotas

#Entry Links

##Create a Link

##Update a Links

##Show a Link

#Statistics

##Show Statistics

##List Statistics

#Recruit

##Show Marketing Info

#Recontact

##List Qualified Respondents

# Demand

#Surveys

##Create a Survey

##Update a Survey

##Show a Survey

##List Surveys By Status

#Qualifications

##Create a Qualification

##Update a Qualification

##List Qualifications
    
#Quotas

##Create a Quota

##Update a Quota

##List Quotas
    
#Exchange Templates

##List Exchange Templates

##Apply an Exchange Template

#Exchange Groups

##Create a Group

##Create an Empty Group

##Update a Group

##Delete a Group

##Add to a Group

##Show a Group

##Remove from a Group

#Non-Exchange Allocations

##Create an Allocation

##Update an Allocation

##Delete an Allocation

##List Allocations

#Non-Exchange Entry Links

##Create a Link

##Update a Link

##Delete a Link

#Feasibility

##Show Time to Completion

##Show Price

##Show Completes per Day

#Recruits

##List Qualified Respondents

#Guides

#Supply

##Market Research Panel Supplier

#Demand

##DIY Market Research Buyer

##Enterprise Market Research Buyer