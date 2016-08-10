#Securing Spring Cloud Microservices With OAuth2

```
curl "web_app:@localhost:8080/oauth/token" -d "grant_type=password&username=reader&password=reader"
curl -H "Authorization: Bearer $TOKEN" "localhost:9090/foo"
```

```
curl "web_app:@localhost:8080/oauth/token" -d "grant_type=password&username=writer&password=writer"
curl -XPOST -H "Authorization: Bearer $TOKEN" "localhost:9090/foo"
```