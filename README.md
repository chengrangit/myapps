This repo contains the source code for alauda wordpress images, a recipe to make a docker  container for Wordpress, using Linux, Apache and MySQL. 
To build an image, make sure you have Docker [installed](http://www.docker.io/gettingstarted/), clone this repo and then run:
```
docker build -rm -t <yourname>/wordpress .
```

To run the image
Then run it, specifying your desired ports! Woo! 
```
docker run --name wordpress -d -p <http_port>:80 <yourname>/wordpress 
```

Check docker logs after running to see MySQL root password and Wordpress MySQL password, as so
```
echo $(docker logs wordpress | grep password)
```
(note: you won't need the mysql root or the wordpress db password normally)


You can shutdown your wordpress container like this:
```
docker stop wordpress
```

And start it back up like this:
```
docker start wordpress
```

Enjoy your wordpress install courtesy of Docker.
