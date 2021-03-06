##Recontact

Recontacts allow buyers to collect a follow-up impression on a respondent they have already interacted with or already have knowledge of.

#### SurveyQualifiedRespondents Model

| Property | Type   | Description                                                 |
|----------|--------|-------------------------------------------------------------|
| IsActive | int    | Indicates whether a respondent qualifies for the recontact. |
| PID      | string | A supplier's unique respondent identifier.                  |

### GET List Qualified Respondents

> Definition

```plaintext
GET  https://api.samplicio.us/Supply/v1/SurveyQualifiedRespondents/BySurveyNumberSupplierCode/{SurveyNumber}/{SupplierCode}?key={APIKey}
```

> Example Request

```shell
curl https://api.samplicio.us/Supply/v1/SurveyQualifiedRespondents/BySurveyNumberSupplierCode/{SurveyNumber}/{SupplierCode}?key={APIKey}
```

```ruby
require 'net/http'

uri = URI('https://api.samplicio.us/Supply/v1/SurveyQualifiedRespondents/BySurveyNumberSupplierCode/{SurveyNumber}/{SupplierCode}?key={APIKey}')

http = Net::HTTP.new(uri.host, uri.port)

http.use_ssl = true

request = Net::HTTP::Get.new(uri.request_uri)

response = http.request(request)  
```

```php
<?php
$response = file_get_contents('https://api.samplicio.us/Supply/v1/SurveyQualifiedRespondents/BySurveyNumberSupplierCode/{SurveyNumber}/{SupplierCode}?key={APIKey}');
?>
```

```python
import requests

response = requests.get('https://api.samplicio.us/Supply/v1/SurveyQualifiedRespondents/BySurveyNumberSupplierCode/{SurveyNumber}/{SupplierCode}?key={APIKey}')
```

```csharp
using System.Net;

WebRequest request = WebRequest.Create("https://api.samplicio.us/Supply/v1/SurveyQualifiedRespondents/BySurveyNumberSupplierCode/{SurveyNumber}/{SupplierCode}?key={APIKey}");

WebResponse response = request.GetResponse();
```

```javascript
const https = require('https');

https.get('https://api.samplicio.us/Supply/v1/SurveyQualifiedRespondents/BySurveyNumberSupplierCode/{SurveyNumber}/{SupplierCode}?key={APIKey}', function(res){
  var response = res;
});
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
    "API Message: SurveyQualifiedRespondentsBySurveyNumberSupplierCode successful."
  ],
  "ResultCount": 4,
  "SurveyQualifiedRespondents": [
    {
      "PID": "1111110",
      "IsActive": true
    },
    {
      "PID": "1111101",
      "IsActive": true
    },
    {
      "PID": "1111001",
      "IsActive": true
    },
    {
      "PID": "1110001",
      "IsActive": true
    }
  ]
}

```

Returns the list of PIDs by supplier for a specific Fulcrum survey when study type is `Recontact`.



#### Arguments

| Property                     | Type     | Required | Description                                                                                                                                  |
|------------------------------|----------|----------|----------------------------------------------------------------------------------------------------------------------------------------------|
| SurveyNumber                 | int      | true     | Unique number associated with the survey.                                                                                                    |
| SupplierCode                 | string   | true     | Unique code associated with the supplier performing the call.               

       
