Dockerfile MongoDB
===========

### Docker Index pull

    docker pull wasabeef/mongodb

### Run

    docker run -p 27017 -d wasabeef/memcached


### Process check

    docker ps
    CONTAINER ID  IMAGE                   COMMAND               CREATED        STATUS         PORTS                NAMES
    b19630838585  wasabeef/mongodb:latest /usr/bin/mongod -  3 seconds ago  Up 2 seconds   0.0.0.0:49163->27017/tcp   desperate_babbage  backstabbing_davinci


### Operation check

    # mongo
    
    MongoDB shell version: 2.4.8
    connecting to: test
    Welcome to the MongoDB shell.
    For interactive help, type "help".
    For more comprehensive documentation, see
    	http://docs.mongodb.org/
    Questions? Try the support group
    	http://groups.google.com/group/mongodb-user
    
    > show dbs
    local	4.076171875GB
    > exit
    bye

