Swift Docker 

How to run it on IBM Bluemix
---------

1. Install Docker and IBM Containers CLI.

2. On a  Terminal, pull  the Swift Docker image
  docker pull plucena/swift

3.  docker Swift image to IBM Bluemix Containers
  cf login https://api.ng.bluemix.net 
  cf ic login
  cf ic cpi plucena/swift registry.ng.bluemix.net/swift:new

4. Get the IMAGE ID for the new container 
  cf ic images

5. Run Docker image on Bluemix 
  cf ic run -it  [IMAGE ID]

