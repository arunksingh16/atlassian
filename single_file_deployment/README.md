
To Generate Jira KeyStore for use. Please note I have used self signed cert for this.

```
# self signed 

keytool -genkey -keyalg RSA -alias selfsigned -keystore keystore.jks -storepass password -validity 360 -keysize 2048
keytool -noprompt -importkeystore -srckeystore jira.jks -destkeystore jira.jks -deststoretype pkcs12 -srcstorepass mypass -deststorepass mypass


# generate keystore
openssl pkcs12 -export -in cert.pem -inkey crtKey.key -name jira > server.p12 -passin pass:mypass -passout pass:mypass

keytool -noprompt -importkeystore -srckeystore server.p12 -destkeystore jira.jks -srcstoretype pkcs12 -alias jira -srcstorepass mypass -deststorepass mypass

keytool -noprompt -import -alias rootCA -keystore jira.jks -trustcacerts -file rootca.pem -storepass mypass

keytool -noprompt -importkeystore -srckeystore jira.jks -destkeystore jira.jks -deststoretype pkcs12 -srcstorepass mypass -deststorepass mypass

```
