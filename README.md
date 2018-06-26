# apache
Includes all scripts for Apache Webserver and Apache TC


# We will be implementing a REverse proxy in front of Tomcat Instance running on 8080/8443.
# The idea is to proxy tomcat HTTPS to Apache HTTPD HTTPS , so if you request

https://localhost/proxy   shoudl return content of https://localhost:8443/examples/servlets/servlet/HelloWorldExample


# Set of command dor SSL cert generation, we will be usin openssl and not keytool , the same certificate willbe use by TC and WS
> openssl req \
       -newkey rsa:2048 -nodes -keyout domain.key \
       -x509 -days 365 -out domain.crt	
> openssl x509 -text -noout -in domain.crt	

> openssl pkcs12 -inkey domain.key -in domain.crt -export -out domain.p12


# Export Variable for APR
export LD_LIBRARY_PATH='$LD_LIBRARY_PATH:/usr/local/apr/lib'

Biblio

-Configuring APR native libraries and references in TC
https://serverfault.com/questions/577616/using-https-between-apache-loadbalancer-and-backends
- Resolve issues with SSL handshake between TC and WS 
https://serverfault.com/questions/577616/using-https-between-apache-loadbalancer-and-backends


