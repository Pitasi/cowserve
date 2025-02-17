# COWSERVE
Serve cowsay messages over http and https
### Usage   
Serve a cowsay message over https on localhost:8080
```    
$ docker run -it -d -p 8080:8080 sabellas/cowserve   
$ curl --insecure http://localhost/
 ____________________________ 
< Cowserve by samuelesabella >
 ---------------------------- 
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w |
                ||     ||
```
Cowsay messages are set using the request path (e.g. retrieving *https://localhost/abc* will return a cowsay "abc" message).
**cowserve** supports default messages by specifiying the environment variable *msg* 
```    
$ docker run -it -p 8080:8080 --rm -e msg="Hello, cowsay!" sabellas/cowserve    
```
The container also supports http by setting the *::http::* tag inside the default message  
```    
$ docker run -it -p 80:8080 --rm -e msg="::http:: Hello, http cowsay!" sabellas/cowserve 
```
### Build the image    
```    
$ sudo docker build . -t sabellas/cowserve    
``` 
