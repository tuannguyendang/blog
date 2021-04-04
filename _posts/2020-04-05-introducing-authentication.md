---
layout: post
title: authentication server
---

 What is Authentication server ? and how can we build Authentication server ? bla bla Authentication server.

### Authentication server

# Symetric and Asymetric:

2.1. Symmetric Encryption: Same key for both encryption and decryption. Only using this for sample demo don’t use for production

2.2. Asymmetric Encryption: Different key between encryption and decryption. Authentication Server using private key
Resource Server using public key for verify token

# Generate keypair:

2.3. Step Generate Keypair:

A. Generate JKS: Using by Auth Server
	keytool -genkeypair -alias ms-oauth-server -keyalg RSA -keypass Nation@123 -keystore auth-server.jks -storepass Day@123

	What is your first and last name?
	  [Unknown]:  Tuan Nguyen
	What is the name of your organizational unit?
	  [Unknown]:  PTIT
	What is the name of your organization?
	  [Unknown]:  PTIT
	What is the name of your City or Locality?
	  [Unknown]:  Sai Gon
	What is the name of your State or Province?
	  [Unknown]:  Sai Gon
	What is the two-letter country code for this unit?
	  [Unknown]:  VN
	Is CN=Tuan Nguyen, OU=PTIT, O=PTIT, L=Sai Gon, ST=Sai Gon, C=VN correct?
B. Generate public key: using by Resource Server
	1. Download https://code.google.com/archive/p/openssl-for-windows/downloads
	2. Get Private and Public Key: keytool -list -rfc --keystore auth-server.jks | "C:\openssl\bin\openssl.exe" x509 -inform pem -pubkey
	3. Get public key only: keytool -list -rfc --keystore auth-server.jks | "C:\openssl\bin\openssl.exe" x509 -inform pem -pubkey -noout

# Authentication server using asymmetric

2.4. Sample Code : Auth Server with grant type password https://github.com/tuannguyendang/microservice/tree/master/auth/src/main/java/com/dangtuan/auth 

- Branch Master: Used Jwt token store. Token generated store in memory.

- Branch oauth2-server-jdbc: Used Jwt token store. Token generated store in MYSQL database.

- For third party application Authentication server must support authentication code and exchange authentication code (Proof key of code exchange)
Research Keycloak...

2.5. Self encoded token JWT (in memory) vs Database

- JWT (in memory) includes all information for Resource Server. no way invalidate token in case hacker get token 

- Database easy validate and make invalidate token because it saves token in database and resource will call API validate token from Auth Server.

- For application running in multiple region we need using distributed database

# Techlology using:

* Spring boot, Spring Oauth2
* Hibernate
* Mysql
* Open source keycloak

### Next post

Leraning and sharing experiences about Gateway: Gateway discovery service:

* How to biuld Authentication server:
* Running and testing Authentication server:
* Using open source Authentication server: [keycloak](https://www.keycloak.org/) (right sidebar).
* [Documents](https://oauth.net/).

### Next next post

Will know after this post.

### Download

Example is developed by me in GitHub <a href="https://github.com/tuannguyendang/microservice/tree/master/auth/src/main/java/com/dangtuan/auth">authentication server repository</a> for downloads and running.

Thanks!
