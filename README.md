# simpleHttpServer
Simple way to set up website with docker.

### With docker-command

    docker run --name my_simplehttpserver -p 8080:80 -v /home/aikain/www:/var/www -d aikain/simplehttpserver:0.1

Just change port (8080) and volume (/home/aikain/www) to match your setup.

You can stop container:

    docker stop my_simplehttpserver
    
And start it again:

    docker start my_simplehttpserver

If you want remove container, stop it and then remove:

    docker stop my_simplehttpserver
    docker rm my_simplehttpserver

### With docker-compose

Make docker-compose.yml-file with content:

    version: "2"
    services:
      www:
        image: aikain/simplehttpserver:0.1
        restart: always
        ports:
          - "8080:80"
        volumes:
          - "/srv/aikain/www:/var/www"

Change port (8080) and volume (/home/aikain/www) to match your setup.

Build and run with docker-compose:

    docker-compose up --build -d

Stop/Start/Restart:

    docker-compose stop
    docker-compose start
    docker-compose restart

Remove:

    docker-compose stop
    docker-compose rm
