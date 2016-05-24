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

6. Now let's run a simple Swift app inside Docker.   The simple app is based on Swift Currasow HTTP project and it is defined on Sources/main.swift.  

        import Glibc
        import Inquiline
        import Curassow
        serve { _ in
        return Response(.Ok, contentType: "text/plain", body: "Hello World")
        }
        

7.  Clone the swift app. It will run on port 8000.

        git clone https://github.com/kylef/Curassow-example-helloworld
        cd Curassow-example-helloworld/Sources
        swift build
        ../.build/debug/HelloWorld

8.  Now, lets  request and  associate an IP for the Swift Docker we've just created. On a separate window, login to Bluemix Containers:

        cf login https://api.ng.bluemix.net 
        cf ic ip request
        cf ic ip list
        cf ic ps
        cf ic ip bind  [IP] [IMAGE_ID]
        
9. Test your app in a browser - http://IP:8000

