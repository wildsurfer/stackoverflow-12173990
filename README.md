README
------

Related to: https://github.com/jwilder/nginx-proxy/issues/804#issuecomment-344362953

1. Run `docker-compose up --build -d`
2. Add `127.0.0.1 foo.mydomain.com bar.mydomain.com` to /etc/hosts
3. Run `curl -H "Origin: http://example.com" -I bar.mydomain.com`

You should see something like this:

```sh
$ curl -H "Origin: http://bar.mydomain.com" -I bar.mydomain.com
HTTP/1.1 200 OK
Server: nginx/1.11.10
Date: Tue, 14 Nov 2017 19:57:04 GMT
Content-Type: text/plain; charset=utf-8
Content-Length: 17
Connection: keep-alive
Access-Control-Allow-Origin: http://bar.mydomain.com
Access-Control-Allow-Methods: GET, POST, OPTIONS, DELETE, PUT
Access-Control-Allow-Credentials: true
Access-Control-Allow-Headers: User-Agent,Keep-Alive,Content-Type
```
