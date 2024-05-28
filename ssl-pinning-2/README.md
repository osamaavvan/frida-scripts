**Convert the Burp .der certificate into .pem**
`openssl x509 -inform DER -in cacert.der -out cacert.pem`

**Copy the content of the .pem certificate, and add the certificate content into the config.js file.**
```
const CERT_PEM = `-----BEGIN CERTIFICATE-----
Content here
-----END CERTIFICATE-----`;
```

**Set the proxy host and port from the config.js file.**
```
const PROXY_HOST = '192.168.0.111';

const PROXY_PORT = 8082;
```
**Finally, run this command.**
```
frida -U -l config.js -l native-tls-hook.js -l android-certificate-unpinning.js -l android-certificate-unpinning-fallback.js -f <package_name>
```
