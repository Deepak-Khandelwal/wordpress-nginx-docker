# wordpress-nginx

How it works?


Step -1 => Download the repo 


             https://github.com/Deepak-Khandelwal/wordpress-nginx.git

Step -2 => Edit start.sh file
             
                WORDPRESS_DB="wordpress"
                WORDPRESS_HOST="your-db-container/host ip"
                WORDPRESS_USER="wp_user"
                WORDPRESS_PASSWORD="password"
                
                
 Step -3=> Edit docker-comversion: "3"
                services:
                     web:
                      build: .
                      ports:
                       - "80:80"
                      links:
                       - db
                     db:
                      image: mysql
                      command: --default-authentication-plugin=mysql_native_password
                      restart: always
                      environment:
                        MYSQL_ROOT_PASSWORD: "your root password"
                        MYSQL_DATABASE: wordpress <same as the start.sh file>
                        MYSQL_USER: wp_user  <same as the start.sh file>
                        MYSQL_PASSWORD: password  <same as the start.sh file>
                      ports:
                        - "3306:3306"pose.yml file
  
    Step -4=> Run the compose file.          
                  
                   docker-compose up
    
    Step -6=> Check on the browser with your host machine ip.
    
                                                      THANK-YOU
           
           
