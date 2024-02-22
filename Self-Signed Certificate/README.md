## Creating a Self-Signed Certificate With OpenSSL
### If necessary, install OpenSSL on your computer(Ubuntu 22.04):
    sudo apt update
    apt show openssl
    sudo apt install openssl -y
    openssl version
### Create your own Certificate Authority(CA). Enter information about your company while creating root.crt file.
    openssl genpkey -algorithm RSA -out root.key -aes256
    openssl req -x509 -new -key root.key -out root.crt -days 365
### Generate a private key, and store it in a file called server.key
    openssl genpkey -des3 -algorithm RSA -pass pass:SomePassword -out server.pass.key -pkeyopt rsa_keygen_bits:2048
    openssl rsa -passin pass:SomePassword -in server.pass.key -out server.key
### Generate a certificate signing request using the server.key file. Store the certificate signing request in a file called server.csr. Enter information about your company when prompted.
    openssl req -new -key server.key -out server.csr
### Generate a self-signed digital certificate from the root.key, root.crt and server.csr files. Store the certificate in a file called server.crt.
    openssl x509 -req -in server.csr -CA root.crt -CAkey root.key -CAcreateserial -out server.crt -days 365
