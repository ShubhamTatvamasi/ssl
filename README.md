# ssl

Generate RSA private key, 4096 bit
```bash
openssl genrsa 4096
```

Generate RSA private key, 2048 bit with password
```bash
openssl genrsa -aes256
```

Save the generated RSA private key
```bash
openssl genrsa -aes256 -out private.pem
```

Generate and save public key from private key
```bash
openssl rsa -in private.pem -outform PEM -pubout -out public.pem
```
---

### Self-Signed Certificate

Get the list of curves available
```bash
openssl ecparam -list_curves
```
> Only `secp384r1` and `prime256v1` keys are compatible with modern browsers

Generate new private key
```bash
openssl ecparam -name secp384r1 -genkey -out ec_key.pem
```

Generate certificate
```bash
openssl req -new -key ec_key.pem -x509 -nodes -days 3650 -out cert.pem
```
---

### OpenSSL DH Parameters

Generate Diffie-Hellman key exchange
```bash
openssl dhparam -out dhparam.pem 4096
```
---

### Speed Test

ecdhp256 vs ecdhp384, operations per second
```bash
openssl speed ecdhp256 ecdhp384
```
