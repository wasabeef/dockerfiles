Dockerfile redis
===========

Run
# docker run -p 6739 -d wasabeef/redis

Process check
# docker ps
CONTAINER ID        IMAGE                   COMMAND                CREATED             STATUS              PORTS                     NAMES
b4e93ef4da01        wasabeef/redis:latest   /usr/sbin/redis-serv   9 seconds ago       Up 9 seconds        0.0.0.0:49158->6379/tcp   backstabbing_davinci

Operation check
# redis-cli -h localhost -p 49158
redis localhost:49158>
redis localhost:49158> set wasa beef
OK
redis localhost:49158> get wasa
"beef"
