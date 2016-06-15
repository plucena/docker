MYSQL Docker - https://hub.docker.com/r/plucena/mysqld
---------------

user: root

password: unasp


How to install it on IBM Bluemix
-----------------

1. Install Bluemix Containers CLI - https://console.ng.bluemix.net/docs/containers/container_cli_cfic.html

2. Login with Bluemix credentials - API endpoint: https://api.ng.bluemix.net

        cf login


3. Get your namespace - $YOURNAMESPACE

        cf ic namespace get
  
        
4. [Optional] If a namespace is displayed from the cf ic namespace get command, take note of that name and skip to the next step. If a namespace is not specified for your organization yet, set one using the following command:

        cf ic namespace set <new_name>
        
        
5.  Copy MySQL to your Bluemix Containers - Use yournamespace from Step 3 

        cf ic cpi plucena/mysqld registry.ng.bluemix.net/$YOURNAMESPACE/mysql:new
        

6.   Get your image id number - $IMAGE_ID

        cf ic images
        
7.   Run your image and get $PID 
        
        cf ic run -p 3306:3306  $IMAGE_ID               

8.  Request an IP for your Docker
       
         cf ic ip request


9.  List available IPs  - $IP
 
        cf ic ip list

10.  Assign IP to tour docker (from Step 9, Step 7)
        
        cf ic ip bind $IP $PID


11.  Login to pma2.mybluemix.net -  Server: $IP , user: root , password: unasp , database: moodle
