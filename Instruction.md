**Build SP-Docker**

#Build Docker image
docker build -t spring-boot-saml2:1.0 .

#Start docker container
docker run -it --rm -p 8080:8080 -t spring-boot-saml2:1.0

**Build SP-Terminal**
- Install java, maven
mvn clean install
cd target
java -jar spring-boot-security-saml-sample-2.1.0.RELEASE.jar


**Step to test**
1. access http://localhost:8080 -> Click Get started
2. checkin https://idp.ssocircle.com  and Start 3rd Party Login
3. browser will send redirect to /idp.ssocircle.com login page
4. login with username and password: username: dohungcuongdev or cuongdo1295  password: Cuong@12101995
5. From there checkin "I am not a robot" and click Continue SAML Single Sign on
6. browser will redirect to http://localhost:8080/landing and show authenticated information
7. You can enter the address bar the URL http://localhost:8080 and see the information still there
8. You can click logout from there and retest from step 1

#Note:
Change the port to be different from 8080 may lead to SSO error, idp.ssocircle.com does not redirect into your SP after logged in successfully