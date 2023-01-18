Backlink: [[Java]], [[SSL]]. [[JKS]], [[SSL Cert]]
The only difference between keysore and truststore is what they store, what is its purpose and how do we use it

2017 shows JKS not very secured: [Youtube - Explain JKS not very secured](https://youtu.be/viOds2uniC0)

keysotre is for storing own application cert, have public key, private key
truststore is for storing CA cert. No private key.

keystore可以看成一個放key的庫，key就是公鑰，私鑰，數字簽名等組成的一個信息。
truststore是放信任的證書的一個store  
truststore和keystore的性質是一樣的，都是存放key的一個倉庫，區別在於，
==truststore裡存放的是只包含公鑰==的數字證書，代表了可以信任的證書，
而==keystore是包含私鑰的==

Keystore 用於存儲特定程序應提供給雙方（服務器或客戶端）以進行驗證的私鑰和身份證書。
Truststore 用於存儲來自認證機構(CA) 的證書，這些證書驗證服務器在SSL 連接中提供的證書。

---

Keystore is used by KeyManager
Truststore is used by TrustManager
PathL: \\Desktop\\program_files\\jdk-17.0.5\\lib\\security
cacerts file contains a list of certs

Server Atuthentication VS Client Authentication

**Server Authen**
KeyManger ==sends== authen credentials to remote host for authen during handshake
TrustManager ==verifies== credentials shared by the server match with the credentials present in the truststore 
If correct -> Allow handshake -> allow connection
If incorrect -> Reject connection

**Client Authen**
Server requires client cert
Server have truststore config, Client have keysotre


![[TrustStoreVSKeyStore2.png]]


|Authen | KeyManager | TrustManager | 
|------------ | ------------| ------------| 
|Server Authen|Sends credentials|Verifies credentials|
|Client Authen (Server requires client cert)|Client have keystore|Server have truststore config

![[ssl_cert.png | 400]]

![[TrustStoreVSKeyStore.png | 500]]