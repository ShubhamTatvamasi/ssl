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

Generate new private key
```bash
openssl ecparam -name secp384r1 -genkey -out ec_key.pem
```

Generate certificate
```bash
openssl req -new -key ec_key.pem -x509 -nodes -days 3650 -out cert.pem
```
---

### OpenSSL Dhparam

Generate Diffie-Hellman key exchange
```
openssl dhparam -out dhparam.pem 4096
```
