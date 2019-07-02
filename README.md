# ssl

Generate RSA private key, 2048 bit
```bash
openssl genrsa
```

Generate RSA private key, 2048 bit with password
```bash
openssl genrsa -aes256
```

Save the generated RSA private key, 2048 bit with password
```bash
openssl genrsa -aes256 -out private.pem
```

Generate and save public key from private key
```bash
openssl rsa -in private.pem -outform PEM -pubout -out public.pem
```
