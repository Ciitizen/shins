---
title: Object Store
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - javascript--nodejs: Node.JS
  - ruby: Ruby
  - python: Python
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<h1 id="Object-Store">Object Store v0.0.1</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

This API specification describes how to interact with the object store.

Base URLs:

* <a href="https://api.ciitizen.com">https://api.ciitizen.com</a>

 License: 

# Authentication

- HTTP Authentication, scheme: bearer 

<h1 id="Object-Store-Resources">Resources</h1>

Available endpoints related to FHIR Resources

## getResourceById

<a id="opIdgetResourceById"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.ciitizen.com/{resourceType}/{id} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://api.ciitizen.com/{resourceType}/{id} HTTP/1.1
Host: api.ciitizen.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.ciitizen.com/{resourceType}/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://api.ciitizen.com/{resourceType}/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://api.ciitizen.com/{resourceType}/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://api.ciitizen.com/{resourceType}/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.ciitizen.com/{resourceType}/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.ciitizen.com/{resourceType}/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /{resourceType}/{id}`

*Get FHIR resource by id*

Retrieves a FHIR resource with the passed in id

<h3 id="getresourcebyid-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|resourceType|path|string|true|Resource type|
|id|path|string|true|ID of FHIR resource|

> Example responses

> 200 Response

```json
{
  "resourceType": "Patient",
  "id": "example",
  "text": {
    "status": "generated",
    "div": "<div xmlns=\"http://www.w3.org/1999/xhtml\">\n\t\t\t<table>\n\t\t\t\t<tbody>\n\t\t\t\t\t<tr>\n\t\t\t\t\t\t<td>Name</td>\n\t\t\t\t\t\t<td>Peter James \n              <b>Chalmers</b> (&quot;Jim&quot;)\n            </td>\n\t\t\t\t\t</tr>\n\t\t\t\t\t<tr>\n\t\t\t\t\t\t<td>Address</td>\n\t\t\t\t\t\t<td>534 Erewhon, Pleasantville, Vic, 3999</td>\n\t\t\t\t\t</tr>\n\t\t\t\t\t<tr>\n\t\t\t\t\t\t<td>Contacts</td>\n\t\t\t\t\t\t<td>Home: unknown. Work: (03) 5555 6473</td>\n\t\t\t\t\t</tr>\n\t\t\t\t\t<tr>\n\t\t\t\t\t\t<td>Id</td>\n\t\t\t\t\t\t<td>MRN: 12345 (Acme Healthcare)</td>\n\t\t\t\t\t</tr>\n\t\t\t\t</tbody>\n\t\t\t</table>\n\t\t</div>"
  },
  "identifier": [
    {
      "use": "usual",
      "type": {
        "coding": [
          {
            "system": "http://hl7.org/fhir/v2/0203",
            "code": "MR"
          }
        ]
      },
      "system": "urn:oid:1.2.36.146.595.217.0.1",
      "value": "12345",
      "period": {
        "start": "2001-05-06"
      },
      "assigner": {
        "display": "Acme Healthcare"
      }
    }
  ],
  "active": true,
  "name": [
    {
      "use": "official",
      "family": "Chalmers",
      "given": [
        "Peter",
        "James"
      ]
    },
    {
      "use": "usual",
      "given": [
        "Jim"
      ]
    },
    {
      "use": "maiden",
      "family": "Windsor",
      "given": [
        "Peter",
        "James"
      ],
      "period": {
        "end": "2002"
      }
    }
  ],
  "telecom": [
    {
      "use": "home"
    },
    {
      "system": "phone",
      "value": "(03) 5555 6473",
      "use": "work",
      "rank": 1
    },
    {
      "system": "phone",
      "value": "(03) 3410 5613",
      "use": "mobile",
      "rank": 2
    },
    {
      "system": "phone",
      "value": "(03) 5555 8834",
      "use": "old",
      "period": {
        "end": "2014"
      }
    }
  ],
  "gender": "male",
  "birthDate": "1974-12-25",
  "_birthDate": {
    "extension": [
      {
        "url": "http://hl7.org/fhir/StructureDefinition/patient-birthTime",
        "valueDateTime": "1974-12-25T14:35:45-05:00"
      }
    ]
  },
  "deceasedBoolean": false,
  "address": [
    {
      "use": "home",
      "type": "both",
      "text": "534 Erewhon St PeasantVille, Rainbow, Vic  3999",
      "line": [
        "534 Erewhon St"
      ],
      "city": "PleasantVille",
      "district": "Rainbow",
      "state": "Vic",
      "postalCode": "3999",
      "period": {
        "start": "1974-12-25"
      }
    }
  ],
  "contact": [
    {
      "relationship": [
        {
          "coding": [
            {
              "system": "http://hl7.org/fhir/v2/0131",
              "code": "N"
            }
          ]
        }
      ],
      "name": {
        "family": "du Marché",
        "_family": {
          "extension": [
            {
              "url": "http://hl7.org/fhir/StructureDefinition/humanname-own-prefix",
              "valueString": "VV"
            }
          ]
        },
        "given": [
          "Bénédicte"
        ]
      },
      "telecom": [
        {
          "system": "phone",
          "value": "+33 (237) 998327"
        }
      ],
      "address": {
        "use": "home",
        "type": "both",
        "line": [
          "534 Erewhon St"
        ],
        "city": "PleasantVille",
        "district": "Rainbow",
        "state": "Vic",
        "postalCode": "3999",
        "period": {
          "start": "1974-12-25"
        }
      },
      "gender": "female",
      "period": {
        "start": "2012"
      }
    }
  ],
  "managingOrganization": {
    "reference": "Organization/1"
  }
}
```

> 404 Response

```json
{
  "resourceType": "OperationOutcome",
  "issue": [
    {
      "severity": "error",
      "code": "not-found",
      "location": [
        "/Organization/test-organization-1"
      ],
      "details": {
        "text": "Resource Id 'test-organization-1' does not exist"
      }
    }
  ]
}
```

> 410 Response

```json
{
  "resourceType": "Organization",
  "id": "test-organization-1",
  "meta": {
    "lastUpdated": "2018-06-20T20:25:50.306Z",
    "version": 1529526350306
  }
}
```

> 500 Response

```json
{
  "resourceType": "OperationOutcome",
  "issue": [
    {
      "severity": "error",
      "code": "exception"
    }
  ]
}
```

<h3 id="getresourcebyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Document retrieved|[resource](#schemaresource)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|A document does not and has never existed for this id|[bundle](#schemabundle)|
|410|[Gone](https://tools.ietf.org/html/rfc7231#section-6.5.9)|Document has been deleted|[bundle](#schemabundle)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Unexpected error|[bundle](#schemabundle)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
external
</aside>

## getEverythingByPatientId

<a id="opIdgetEverythingByPatientId"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.ciitizen.com/Patient/{id}/$everything \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://api.ciitizen.com/Patient/{id}/$everything HTTP/1.1
Host: api.ciitizen.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.ciitizen.com/Patient/{id}/$everything',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://api.ciitizen.com/Patient/{id}/$everything',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://api.ciitizen.com/Patient/{id}/$everything',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://api.ciitizen.com/Patient/{id}/$everything', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.ciitizen.com/Patient/{id}/$everything");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.ciitizen.com/Patient/{id}/$everything", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /Patient/{id}/$everything`

*Get everything for a specific patient*

Retrieves everything for a specific patient and puts it in a FHIR bundle

<h3 id="geteverythingbypatientid-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|ID of FHIR resource|

> Example responses

> 200 Response

```json
{
  "resourceType": "Bundle",
  "identifier": "166ed92d-4de7-452e-a536-ba56a27f7d80",
  "type": "searchset",
  "entry": [],
  "total": 0
}
```

> 500 Response

```json
{
  "resourceType": "OperationOutcome",
  "issue": [
    {
      "severity": "error",
      "code": "exception"
    }
  ]
}
```

<h3 id="geteverythingbypatientid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returned everything for the patient|[bundle](#schemabundle)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Unexpected error|[bundle](#schemabundle)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
external
</aside>

## searchResources

<a id="opIdsearchResources"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://api.ciitizen.com/{resourceType}/_search \
  -H 'Content-Type: application/x-www-form-urlencoded' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://api.ciitizen.com/{resourceType}/_search HTTP/1.1
Host: api.ciitizen.com
Content-Type: application/x-www-form-urlencoded
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.ciitizen.com/{resourceType}/_search',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 0,
  "entry": []
}';
const headers = {
  'Content-Type':'application/x-www-form-urlencoded',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://api.ciitizen.com/{resourceType}/_search',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/x-www-form-urlencoded',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://api.ciitizen.com/{resourceType}/_search',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/x-www-form-urlencoded',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://api.ciitizen.com/{resourceType}/_search', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.ciitizen.com/{resourceType}/_search");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/x-www-form-urlencoded"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.ciitizen.com/{resourceType}/_search", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /{resourceType}/_search`

*Search for FHIR resources*

Returns search results in a FHIR bundle

> Body parameter

```yaml
resourceType: Bundle
type: searchset
total: 0
entry: []

```

<h3 id="searchresources-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[bundle](#schemabundle)|false|none|
|resourceType|path|string|true|Resource type|

> Example responses

> 200 Response

```json
{
  "resourceType": "Patient",
  "id": "example",
  "text": {
    "status": "generated",
    "div": "<div xmlns=\"http://www.w3.org/1999/xhtml\">\n\t\t\t<table>\n\t\t\t\t<tbody>\n\t\t\t\t\t<tr>\n\t\t\t\t\t\t<td>Name</td>\n\t\t\t\t\t\t<td>Peter James \n              <b>Chalmers</b> (&quot;Jim&quot;)\n            </td>\n\t\t\t\t\t</tr>\n\t\t\t\t\t<tr>\n\t\t\t\t\t\t<td>Address</td>\n\t\t\t\t\t\t<td>534 Erewhon, Pleasantville, Vic, 3999</td>\n\t\t\t\t\t</tr>\n\t\t\t\t\t<tr>\n\t\t\t\t\t\t<td>Contacts</td>\n\t\t\t\t\t\t<td>Home: unknown. Work: (03) 5555 6473</td>\n\t\t\t\t\t</tr>\n\t\t\t\t\t<tr>\n\t\t\t\t\t\t<td>Id</td>\n\t\t\t\t\t\t<td>MRN: 12345 (Acme Healthcare)</td>\n\t\t\t\t\t</tr>\n\t\t\t\t</tbody>\n\t\t\t</table>\n\t\t</div>"
  },
  "identifier": [
    {
      "use": "usual",
      "type": {
        "coding": [
          {
            "system": "http://hl7.org/fhir/v2/0203",
            "code": "MR"
          }
        ]
      },
      "system": "urn:oid:1.2.36.146.595.217.0.1",
      "value": "12345",
      "period": {
        "start": "2001-05-06"
      },
      "assigner": {
        "display": "Acme Healthcare"
      }
    }
  ],
  "active": true,
  "name": [
    {
      "use": "official",
      "family": "Chalmers",
      "given": [
        "Peter",
        "James"
      ]
    },
    {
      "use": "usual",
      "given": [
        "Jim"
      ]
    },
    {
      "use": "maiden",
      "family": "Windsor",
      "given": [
        "Peter",
        "James"
      ],
      "period": {
        "end": "2002"
      }
    }
  ],
  "telecom": [
    {
      "use": "home"
    },
    {
      "system": "phone",
      "value": "(03) 5555 6473",
      "use": "work",
      "rank": 1
    },
    {
      "system": "phone",
      "value": "(03) 3410 5613",
      "use": "mobile",
      "rank": 2
    },
    {
      "system": "phone",
      "value": "(03) 5555 8834",
      "use": "old",
      "period": {
        "end": "2014"
      }
    }
  ],
  "gender": "male",
  "birthDate": "1974-12-25",
  "_birthDate": {
    "extension": [
      {
        "url": "http://hl7.org/fhir/StructureDefinition/patient-birthTime",
        "valueDateTime": "1974-12-25T14:35:45-05:00"
      }
    ]
  },
  "deceasedBoolean": false,
  "address": [
    {
      "use": "home",
      "type": "both",
      "text": "534 Erewhon St PeasantVille, Rainbow, Vic  3999",
      "line": [
        "534 Erewhon St"
      ],
      "city": "PleasantVille",
      "district": "Rainbow",
      "state": "Vic",
      "postalCode": "3999",
      "period": {
        "start": "1974-12-25"
      }
    }
  ],
  "contact": [
    {
      "relationship": [
        {
          "coding": [
            {
              "system": "http://hl7.org/fhir/v2/0131",
              "code": "N"
            }
          ]
        }
      ],
      "name": {
        "family": "du Marché",
        "_family": {
          "extension": [
            {
              "url": "http://hl7.org/fhir/StructureDefinition/humanname-own-prefix",
              "valueString": "VV"
            }
          ]
        },
        "given": [
          "Bénédicte"
        ]
      },
      "telecom": [
        {
          "system": "phone",
          "value": "+33 (237) 998327"
        }
      ],
      "address": {
        "use": "home",
        "type": "both",
        "line": [
          "534 Erewhon St"
        ],
        "city": "PleasantVille",
        "district": "Rainbow",
        "state": "Vic",
        "postalCode": "3999",
        "period": {
          "start": "1974-12-25"
        }
      },
      "gender": "female",
      "period": {
        "start": "2012"
      }
    }
  ],
  "managingOrganization": {
    "reference": "Organization/1"
  }
}
```

> 400 Response

```json
{
  "resourceType": "OperationOutcome",
  "issue": [
    {
      "severity": "error",
      "code": "required",
      "location": [
        "/Patient/_search"
      ],
      "details": {
        "text": "No search criteria provided"
      }
    }
  ]
}
```

> 500 Response

```json
{
  "resourceType": "OperationOutcome",
  "issue": [
    {
      "severity": "error",
      "code": "exception"
    }
  ]
}
```

<h3 id="searchresources-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Search returned|[bundle](#schemabundle)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|No search parameters provided|[bundle](#schemabundle)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Unexpected error|[bundle](#schemabundle)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
external
</aside>

# Schemas

<h2 id="tocSresource">resource</h2>

<a id="schemaresource"></a>

```json
{
  "id": "string",
  "resourceType": "string",
  "meta": {
    "created": "2018-06-20T21:24:05Z",
    "lastUpdated": "2018-06-20T21:24:05Z",
    "lastUpdatedBy": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuidv4)|false|none|Document identifier|
|resourceType|string|false|read-only|Resource type|
|meta|object|false|none|none|
|» created|string(date-time)|false|none|date when the resource was created|
|» lastUpdated|string(date-time)|false|none|date when the resource was last updated|
|» lastUpdatedBy|string(uuidv4)|false|none|identifier of the agent that performed the last update|

<h2 id="tocSbundle">bundle</h2>

<a id="schemabundle"></a>

```json
{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 0,
  "entry": []
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|resourceType|string|false|none|The type of FHIR resource. This will always be "Bundle"|
|identifier|string|false|none|A unique identifier of this bundle|
|type|string|false|none|The type of FHIR bundle. This will always be "searchset"|
|total|integer|false|none|The total number of entries in the "entry" array|
|entry|[object]|false|none|A list of FHIR resource objects|

