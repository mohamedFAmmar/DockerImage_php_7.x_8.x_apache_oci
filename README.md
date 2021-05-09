# Docker image for latest php 7.x and 8.x with apache with OCI8
---	
* Latest PHP 7.2 image with Apache and Oracle oci8 (instantclient 12.2.0.1.0)
* Latest PHP 7.3 image with Apache and Oracle oci8 (instantclient 12.2.0.1.0)
* Latest PHP 7.4 image with Apache and Oracle oci8 (instantclient 12.2.0.1.0)
* Latest PHP 8.0 image with Apache and Oracle oci8 (instantclient 12.2.0.1.0)

This image is built from [official PHP images](https://hub.docker.com/_/php/). It adds oci8 drivers to official image to connect to Oracle database.

## Steps for running docker
simple steps to do this <br/>
1- Install docker as [docker documentations](https://docs.docker.com/engine/install/) <br>
2- Download package <br>
3- Build image <br>
4- Run docker image <br>
5- Test on open browser <br>

## 3- Build image
```
docker build --file ./php72/Dockerfile -t php72 .
docker build --file ./php73/Dockerfile -t php73 . 
docker build --file ./php74/Dockerfile -t php74 . 
docker build --file ./php80/Dockerfile -t php80 . 
```

## 4- Run docker image
```
docker run -dt --name=php72 -p 8072:80 php72
docker run -dt --name=php73 -p 8073:80 php73
docker run -dt --name=php74 -p 8074:80 php74
docker run -dt --name=php80 -p 8081:80 php80
```
## 5- Test on open browser
http://localhost:8072/phpinfo.php <br/>
http://localhost:8073/phpinfo.php <br/>
http://localhost:8074/phpinfo.php <br/>
http://localhost:8081/phpinfo.php <br/>

## Mount projects folder as a web root 
```
docker run -dt --name=php73 -v <projects_folder_full_path>:/vaw/www/html -p 8073:80 php73
```
