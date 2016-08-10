#Securing Spring Cloud Microservices With OAuth2

```
run the command : keytool -genkeypair -alias jwt -keyalg RSA -dname "CN=jwt, L=BH, S=BH, C=BR" -keypass mySecretKey -keystore jwt.jks -storepass mySecretKey

run the command : keytool -list -rfc --keystore jwt.jks | openssl x509 -inform pem -pubkey

jwt.jks copy this file to src/main/resources in project oauth2-server

create public.cert file and copy to src/main/resources in project oauth2-resource-server
```



```
curl "web_app:@localhost:8080/oauth/token" -d "grant_type=password&username=reader&password=reader"
curl -H "Authorization: Bearer $TOKEN" "localhost:9090/foo"
```

```
curl "web_app:@localhost:8080/oauth/token" -d "grant_type=password&username=writer&password=writer"
curl -XPOST -H "Authorization: Bearer $TOKEN" "localhost:9090/foo"
```