 

 
******************************************

***********************************
Run the mysql container with external volume

C:\Docker-Share\data\mysqldata

docker run --name app-mysql --volume /c/Docker-Share/data/mysqldata:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=MyRootPass123 -e MYSQL_DATABASE=user_data -e MYSQL_USER=app-user -e MYSQL_PASSWORD=MyRootPass123 -d mysql:5.6

docker logs app-mysql

Copy the file from host machine to the container

docker cp table.sql app-mysql:/table.sql
docker cp records.sql app-mysql:/records.sql 



docker exec -it app-mysql bash

Run mysql commands on the MySQl database inside the container

To import and execute sql  script in database container.
Run these from bash terminal to import sql script file into Database

mysql -uroot -p user_data < table.sql

mysql -uroot -p user_data < records.sql  


mysql -uroot -p user_data -e "SELECT DATABASE()"

mysql -uroot -p user_data -e "SELECT VERSION()"



mysql -uroot -p user_data -e "describe appusers"  


mysql -uroot -p user_data  -e "select * from user_data.appusers"  

exit

*************************************************************
  
To build the api-web-war app as container image    

 To build the webapp with tag

docker build -t web-db-app -f Dockerfile-WebApp-MySQL-Localhost.txt .



To Run the web-db-app image in detacheed mode with host port mapping/forwarding with link to Mysql container app-mysql as localhost host name.

docker run -p 9090:8090 --name user-app --link app-mysql:localhost -d web-db-app

Check the application log by
 
docker logs user-app 
 
docker exec -it user-app bash

Open in browser  

http://localhost:9090/webapp-mysql/users/update 


To post new data with post method

http://localhost:9090/webapp-mysql/users/add

http://localhost:9090/webapp-mysql/users/getUser/1


 After successful testing of user-db-app, push this image to docker-hub


 docker tag web-db-app pbadhe34/training:web-mysql-local
 docker login

 docker push pbadhe34/training:web-mysql-local

 
 