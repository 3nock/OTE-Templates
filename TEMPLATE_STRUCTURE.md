# OSINT Template Engine's Template Structure

The OSINT Template Engine templates are written in `json` and have a `.json` extension and are located in the `ote/templates/` folder by default.

The templates have a very simple and direct structure consisting of 4 major parts.
- [Info](#info)
- [Author](#author)
- [Authentication](#authentication)
- [Endpoints](#endpoints)

## The general structure:

The overall structure of OSINT Template Engine's json template.

```json
{
    "authentication": {
        "authHeader": "name of authentication header if there is one",
        "authType": "api authentication type",
        "link": "link to obtain the credentials",
        "uses_id": false,
        "uses_key": false
    },
    "author": {
        "name": "name of the author",
        "social": "social or email link of the author"
    },
    "endpoints": [
        {
            "description": "description of the endpoint",
            "extractors": [
                {
                    "name": "name of the extractor",
                    "script": "extraction script (either json or xml)"
                }
            ],
            "inputTypes": [
                "input types accepted by the API endpoint"
            ],
            "link": "link of the API endpoint",
            "name": "name of the API endpoint",
            "postData": "request's post data is request type is a post request",
            "responseType": "response type expected",
            "resquestType": "request type, either post or get"
        }
    ],
    "info": {
        "description": "summary description of the template",
        "documentation": "link to the documentaion of the templates's APIs",
        "link": "link to the main site of the template",
        "name": "name of the template"
    }
}
```

## Author

This section contains the information about the author of the template including;
- `name` - Name of the author of the template
- `social` - social media link or email of the template's author.
e.g. 
```json
"author": {
        "name": "Enock N. M.",
        "social": "https://github.com/3nock"
}
```

## Info

This section contains the basic information about the template including;
- `name` - of the template
- `description` - A short summary/description about the template.
- `Link` - URL link to the main site of the particular template.
- `Documentation` - URL link to the online API documentation of the template's APIs.
e.g.
```json
"info": {
    "name": "ote",
    "description": "OTE is a next generation information gathering framework",
    "documentation": "https://spidersuite.github.io/ote/doc",
    "link": "https://spidersuite.github.io/ote"
}
```

## Authentication

This section contains template's API authentication information if the template uses one. Some template sources require API key or Authentication credentials for you to be able to query their API successfuly.
- `authHeader` - Name of authentication header if the template uses header authentication",
- `authType` - Type of API authentication that the template uses, can be either; `query string` authentication meaning the API key is coupled inside the request url or data, `basic` authentication, `bearer authorization` authentication or using a custom header for authentication.
- `link` - link to where one can obtain the authentication credentials such us API keys.
- `uses_id` - **true** if the template uses an id or name for authentication.
- `uses_key` - **true** if the template uses api key, password or secret for authentication.

e.g.
```json
"authentication": {
    "uses_id": false,
    "uses_key": true,
    "link": "https://spidersuite.github.io/OTE/register",
    "authType": "HEADER",
    "authHeader": "X-API-Key"
}
```

## Endpoints

This section contains the list of API endpoints that the template offers. Each template provides a different number of api endpoints.

- `name` - name of the API endpoint.
- `description` - description about the endpoint, copy and paste from the description the api documentation if available.
- `responseType` - response type expected.
- `resquestType` - request type, either post or get.
- `link` - link of the API endpoint.
- `postData` - request's post data is request type is a post request.
- `inputTypes` - list of input types accepted by the API endpoint. e.g. ip,asn,domain etc.

### Extractors

This are scripts used to extract specific key information from API endpoint results. currently supporting json and xml only.
- `name` - name of the extractor
- `script` - extraction script (either json or xml).

e.g.
```json
"endpoints": [
    {
        "name": "Subdomains Enumeration",
        "description": "retuns all sudomains of the target domain",
        "resquestType": "GET",
        "responseType": "JSON",
        "link": "https://api.ote.com/subdomains?domain={{input}}&api_key={{key}}",
        "postData": "",
        "inputTypes": [
            "domain"
        ],
        "extractors": [
            {
                "name": "subdomain",
                "script": "{\"subdomains\":[\"$$\"]}"
            }
        ]
    }
]
```