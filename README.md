# SafeTransaction
Demo for safe transaction with TLS, RSA, JWS

## Project Structure
```
SSL Certificate, Signing Certificate, CA Certificate
Project must have ServerA and ServerB
Test script
    1. Can handshake
    2. Can encrypt
    3. Can decrypt
    4. Can verify signing

project/
    script/
        start_all_server.sh
        shutdown_all_server.sh
        start_database.sh
        shutdown_database.sh
    Bank/
        springBoot
            controller/
                PaymentController.java
                    POST /book/req/pay
                AbstractCertificateApi.java
                    generateKeyPair()
                    generateCsr()
                    uploadCertificate()
                    getKeyPair()
                    getCsr()
                SslCertificateController.java
                    GET /ssl/key-pair
                    GET /ssl/csr
                    GET /ssl/certificate
                    POST /ssl/key-pair
                    POST /ssl/csr
                    POST /ssl/certificate/upload
                CaCertificateController.java
                    GET /ca/key-pair
                    GET /ca/csr
                    GET /ca/certificate
                    POST /ca/key-pair
                    POST /ca/csr
                    POST /ca/certificate/upload
                SigningCertificateController.java
                    GET /signing/key-pair
                    GET /signing/csr
                    GET /signing/certificate
                    POST /signing/key-pair
                    POST /signing/csr
                    POST /signing/certificate/upload
            utils/
                CipherUtils.java
                    String generatePrivateKey()
                    String extractPublicKey(privateKey)
                    String encrypt(plainText)
                    String decrypt(encryptedText)

                JwsUtils.java

                JsonUtils.java
                    String toJson(Object obj)
                    String toJson(Object obj, String defaultValue)
                    String toJson(Object obj, Exception e)
                    Map<String, Object> readToMap(String json)
                    Object readToObj(String json, String classPath) 
                OkHttpUtils.java
                    get()
                    post()

            service/
                PaymentService.java
                JwsService.java
            model/
                entity/
                    SslCertificate.java
                    CaCertificate.java
                    SigningCertificate.java
                dao/
                    SslCertificateDao.java
                    CaCertificateDao.java
                    SigningCertificateDao.java
                repository/
                    SslCertificateRepository.java
                    CaCertificateRepository.java
                    SigningCertificateRepository.java



    Merchant/
        springBoot
            controller/
                OrderController.java
                    POST /order/create
                    POST /order/payment
                    POST /order/delete

            utils/
                CipherUtils.java
                    String generatePrivateKey()
                    String extractPublicKey(privateKey)
                    String encrypt(plainText)
                    String decrypt(encryptedText)

                JwsUtils.java

                JsonUtils.java
                    String toJson(Object obj)
                    String toJson(Object obj, String defaultValue)
                    String toJson(Object obj, Exception e)
                    Map<String, Object> readToMap(String json)
                    Object readToObj(String json, String classPath) 
                OkHttpUtils.java
                    get()
                    post()

            service/
                PaymentService.java
                JwsService.java
            model/
                entity/
                    SslCertificate.java
                    CaCertificate.java
                    SigningCertificate.java
                dao/
                    SslCertificateDao.java
                    CaCertificateDao.java
                    SigningCertificateDao.java
                repository/
                    SslCertificateRepository.java
                    CaCertificateRepository.java
                    SigningCertificateRepository.java

```
