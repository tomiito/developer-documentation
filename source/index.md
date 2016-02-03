---
title: Fulcrum API Documentation

language_tabs:
  - shell : curl
  - ruby : Ruby
  - php : PHP
  - python : Python
  - csharp : C#

toc_footers:
  - <a href='https://luc.id/fulcrum/'>Get access to Fulcrum APIs</a>

includes:
  - errors
  
search: true
---
# Introduction

Lucid brings efficiency and automation to online sampling with Fulcrum, today’s most powerful, open, and customizable online sampling platform.
    
The API is based on REST (REpresentational State Transfer) principles, which makes it very easy to write and test applications. Both JSON and XML data formats are supported.

# Guides

# Authentication

> To authorize, use this code:

```shell
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```ruby
class Greeter
  def initialize(name="World")
    @name = name
  end

  def say_hi
    puts "Hi #{@name}!"
  end
end
```

```php
<?php
  print("Hello {$world}");
?>
```

```python
def fib(n):    # write Fibonacci series up to n
    """Print a Fibonacci series up to n."""
    a, b = 0, 1
    while a < n:
        print a,
        a, b = b, a+b
```

```csharp
// reverse byte order (16-bit)
public static UInt16 ReverseBytes(UInt16 value)
{
  return (UInt16)((value & 0xFFU) << 8 | (value & 0xFF00U) >> 8);
}
```

> Make sure to replace `meowmeowmeow` with your API key.

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