Swift Docker -  IBM Bluemix install
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

6. Now let's clone a simple server app, compile and run it. The simple app is based on Swift Currasow HTTP project and it is defined on Sources/main.swift.  

        import Glibc
        import Inquiline
        import Curassow
        serve { _ in
        return Response(.Ok, contentType: "text/plain", body: "Hello World")
        }
        

7. 
