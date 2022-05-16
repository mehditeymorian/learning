# Curl

<p align="center">
  <img src="../assets/curl-logo.png" />
</p>

**Note**: We will use [JsonPlaceholder](https://jsonplaceholder.typicode.com/) as a server to send requests.
It is free and easy to use.


## Simple command
Request
```shell
curl https://jsonplaceholder.typicode.com/posts/3
```

Response
```http
{
  "userId": 1,
  "id": 3,
  "title": "ea molestias quasi exercitationem repellat qui ipsa sit aut",
  "body": "et iusto sed quo iure\nvoluptatem occaecati omnis eligendi aut ad\nvoluptatem doloribus vel accusantium quis pariatur\nmolestiae porro eius odio et labore et velit aut"
}
```

## Response & Headers
Request
```shell
curl -i https://jsonplaceholder.typicode.com/posts/3
```

Response
```http
HTTP/2 200 
date: Sun, 13 Feb 2022 07:03:09 GMT
content-type: application/json; charset=utf-8
content-length: 283
x-powered-by: Express
x-ratelimit-limit: 1000
x-ratelimit-remaining: 999
x-ratelimit-reset: 1640112836
vary: Origin, Accept-Encoding
access-control-allow-credentials: true
cache-control: max-age=43200
pragma: no-cache
expires: -1
x-content-type-options: nosniff
etag: W/"11b-USacuIw5a/iXAGdNKBvqr/TbMTc"
via: 1.1 vegur
cf-cache-status: HIT
age: 512
accept-ranges: bytes
expect-ct: max-age=604800, report-uri="https://report-uri.cloudflare.com/cdn-cgi/beacon/expect-ct"
report-to: ...
nel: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
server: cloudflare
cf-ray: 6dcc31fb2eb77750-LHR
alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400

{
  "userId": 1,
  "id": 3,
  "title": "ea molestias quasi exercitationem repellat qui ipsa sit aut",
  "body": "et iusto sed quo iure\nvoluptatem occaecati omnis eligendi aut ad\nvoluptatem doloribus vel accusantium quis pariatur\nmolestiae porro eius odio et labore et velit aut"
}
```

## Only Headers
Request
```shell
curl -I https://jsonplaceholder.typicode.com/posts/3
curl --head https://jsonplaceholder.typicode.com/posts/3
```

Response
```http
HTTP/2 200 
date: Sun, 13 Feb 2022 07:03:09 GMT
content-type: application/json; charset=utf-8
content-length: 283
x-powered-by: Express
x-ratelimit-limit: 1000
x-ratelimit-remaining: 999
x-ratelimit-reset: 1640112836
vary: Origin, Accept-Encoding
access-control-allow-credentials: true
cache-control: max-age=43200
pragma: no-cache
expires: -1
x-content-type-options: nosniff
etag: W/"11b-USacuIw5a/iXAGdNKBvqr/TbMTc"
via: 1.1 vegur
cf-cache-status: HIT
age: 512
accept-ranges: bytes
expect-ct: max-age=604800, report-uri="https://report-uri.cloudflare.com/cdn-cgi/beacon/expect-ct"
report-to: ...
nel: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
server: cloudflare
cf-ray: 6dcc31fb2eb77750-LHR
alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400
```

## Save Output to file
Request
```shell
curl -o result.txt https://jsonplaceholder.typicode.com/posts
curl --output result.txt https://jsonplaceholder.typicode.com/posts
```

Response
```text
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   283  100   283    0     0    563      0 --:--:-- --:--:-- --:--:--   563
```
there should be a file named `result.txt` with downloaded posts in it.

## Direct Download
This command is the same as previous one except it doesn't require a name.

Request
```shell
curl -O https://jsonplaceholder.typicode.com/posts
```

Response
```text
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   283  100   283    0     0    563      0 --:--:-- --:--:-- --:--:--   563
```

**Options**: you can use `--limit-rate X` for example `--limit-rate 1000B` to limit the downloading rate.

## POST Request
Request
```shell
curl --data "title=Hello&body=World&field=value" https://jsonplaceholder.typicode.com/posts
curl -d "title=Hello&body=World&field=value" https://jsonplaceholder.typicode.com/posts
```

Response
```json
{
  "title": "Hello",
  "body": "World",
  "field": "value",
  "id": 101
}
```

## PUT Request
Request
```shell
curl -X PUT --data "title=Hello" https://jsonplaceholder.typicode.com/posts/3
curl -X PUT -d "title=Hello" https://jsonplaceholder.typicode.com/posts/3
```

Response
```json
{
  "title": "Hello",
  "id": 3
}
```

## DELETE Request
Request
```shell
curl -X DELETE https://jsonplaceholder.typicode.com/posts/3
curl -X DELETE https://jsonplaceholder.typicode.com/posts/3
```

Response
```json
{}
```

## Authentication
Request
```shell
curl -u username:password https://ADDRESS
```

## Redirect
Request
```shell
curl -L google.com
```
**Note**: test without `-L` to see the difference
