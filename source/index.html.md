---
title: API Reference

language_tabs: # must be one of https://github.com/rouge-ruby/rouge/wiki/List-of-supported-languages-and-lexers
  - shell

toc_footers:
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  # - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the Link tracker API
---

# Introduction


Welcome to the LinkTracker API! Our API provides a comprehensive solution for tracking and analyzing web links across various digital platforms. Whether you're looking to monitor click-through rates, understand audience engagement, or track the performance of your marketing campaigns, LinkTracker has got you covered.

# Authentication

> This API does not require authentication


This API does not require authentication


# Links

## Get All Links


```shell
curl --request GET \
  --url http://localhost:3000/api/v1/links?page=1
```

> The above command returns JSON structured like this:

```json

[
	{
		"id": 1,
		"original_url": "https://google.com/",
		"short_url": "http://localhost:3000/onI52uQ",
		"token": "onI52uQ",
		"analytics_count": 0,
		"updated_at": "2024-02-09T06:38:12.777Z",
		"created_at": "2024-02-09T06:38:12.777Z"
	},
	{
		"id": 2,
		"original_url": "https://google.com/",
		"short_url": "http://localhost:3000/asdEWQ13",
		"token": "asdEWQ13",
		"analytics_count": 0,
		"updated_at": "2024-02-09T06:38:12.772Z",
		"created_at": "2024-02-09T06:38:12.771Z"
	},
]
```

This endpoint retrieves all links.

### HTTP Request

`GET http://localhost:3000/api/v1/links`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
page | true | You can use this parameter to paginate through the results. The default is 1.


## Get a Specific Link


```shell
curl --request GET \
  --url http://localhost:3000/api/v1/links/60
```

> The above command returns JSON structured like this:

```json
{
  "id": 60,
	"original_url": "https://google.com/",
	"short_url": "http://localhost:3000/onI52uQ",
	"token": "onI52uQ",
	"analytics_count": 0,
	"updated_at": "2024-02-09T06:38:12.777Z",
	"created_at": "2024-02-09T06:38:12.777Z"
}
```

This endpoint retrieves a link.

### HTTP Request

`GET http://localhost:3000/api/v1/links/<ID>`

### Query Parameters

Parameter  | Description
---------  | -----------
ID | The ID of the link to retrieve


## Update a Specific Link


```shell
curl --request PATCH \
  --url http://localhost:3000/api/v1/links/20 \
  --header 'Content-Type: application/json' \
  --data '{"link": {"original_url": "https://new_url.com/"}}'
```

This endpoint update a link.


### HTTP Request

`PATCH http://localhost:3000/api/v1/links/<ID>`

### Query Parameters

Parameter  | Description
---------  | -----------
ID | The ID of the link to update

### Body Parameters

Parameter  | Description
---------  | -----------
"link": "original_url" | The url to be updated


## Create a Link


```shell
curl --request POST \
  --url http://localhost:3000/api/v1/links \
  --header 'Content-Type: application/json' \
  --data '{"link": {"original_url": "https://google.com/"}}'
```

This endpoint creates a link.

### HTTP Request

`POST http://localhost:3000/api/v1/links`

### Body Parameters

Parameter  | Description
---------  | -----------
"link": "original_url" | The url to be shortened

> The above command returns JSON structured like this:

```json
{
  "id": 60,
	"original_url": "https://google.com/",
	"short_url": "http://localhost:3000/onI52uQ",
	"token": "onI52uQ",
	"analytics_count": 0,
	"updated_at": "2024-02-09T06:38:12.777Z",
	"created_at": "2024-02-09T06:38:12.777Z"
}
```

## Delete a Specific Link

```shell
curl "http://localhost:3000/api/v1/links/5" \
  -X DELETE 
```



This endpoint deletes a specific link.

### HTTP Request

`DELETE http://localhost:3000/api/v1/links/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the link to delete

# Analytics

## Get Analytics from Link


```shell
curl --request GET \
  --url http://localhost:3000/api/v1/links/1/analytics?page=1
```

> The above command returns JSON structured like this:

```json
[
	{
		"id": 1,
		"system_name": "macOS",
		"browser_name": "Chrome",
		"browser_version": "121.0.0.0",
		"referer": null,
		"country": null,
		"region": null,
		"city": null,
		"latitude": null,
		"longitude": null,
		"ip": "172.17.0.1",
		"device": "mac",
		"created_at": "2024-02-12T00:11:49.655Z"
	},
	{
		"id": 2,
		"system_name": "macOS",
		"browser_name": "Chrome",
		"browser_version": "121.0.0.0",
		"referer": null,
		"country": null,
		"region": null,
		"city": null,
		"latitude": null,
		"longitude": null,
		"ip": "172.17.0.1",
		"device": "mac",
		"created_at": "2024-02-12T00:11:50.342Z"
	},
	{
		"id": 3,
		"system_name": "macOS",
		"browser_name": "Chrome",
		"browser_version": "121.0.0.0",
		"referer": null,
		"country": null,
		"region": null,
		"city": null,
		"latitude": null,
		"longitude": null,
		"ip": "172.17.0.1",
		"device": "mac",
		"created_at": "2024-02-12T00:11:51.036Z"
	},
	{
		"id": 4,
		"system_name": "macOS",
		"browser_name": "Chrome",
		"browser_version": "121.0.0.0",
		"referer": null,
		"country": null,
		"region": null,
		"city": null,
		"latitude": null,
		"longitude": null,
		"ip": "172.17.0.1",
		"device": "mac",
		"created_at": "2024-02-12T00:11:51.639Z"
	},
	{
		"id": 5,
		"system_name": "macOS",
		"browser_name": "Chrome",
		"browser_version": "121.0.0.0",
		"referer": null,
		"country": null,
		"region": null,
		"city": null,
		"latitude": null,
		"longitude": null,
		"ip": "172.17.0.1",
		"device": "mac",
		"created_at": "2024-02-12T00:11:52.023Z"
	}
]
```

This endpoint retrieves analytics fom link.

### HTTP Request

`GET http://localhost:3000/api/v1/links/<ID>/analytics`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
ID | true | You can use this parameter to paginate through the results. The default is 1.
page | true | You can use this parameter to paginate through the results. The default is 1.

