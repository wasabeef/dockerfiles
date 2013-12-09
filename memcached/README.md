Dockerfile redis
===========

### Docker Index pull

    docker pull wasabeef/memcached

### Run

    docker run -p 11211 -d wasabeef/memcached


### Process check

    docker ps
    CONTAINER ID  IMAGE                   COMMAND               CREATED        STATUS         PORTS                NAMES
    b19630838585  wasa/mem:latest         /usr/bin/memcached -  3 seconds ago  Up 2 seconds   0.0.0.0:49161->11211/tcp   desperate_babbage  backstabbing_davinci


### Operation check

    # telnet localhost 49161
    Trying ::1...
    Connected to localhost.
    Escape character is '^]'.
    
    stats
    
    STAT pid 1
    STAT uptime 14
    STAT time 1386576923
    STAT version 1.4.4
    STAT pointer_size 64
    STAT rusage_user 0.017997
    STAT rusage_system 0.017997
    STAT curr_connections 10
    STAT total_connections 11
    STAT connection_structures 11
    STAT cmd_get 0
    STAT cmd_set 0
    STAT cmd_flush 0
    STAT get_hits 0
    STAT get_misses 0
    STAT delete_misses 0
    STAT delete_hits 0
    STAT incr_misses 0
    STAT incr_hits 0
    STAT decr_misses 0
    STAT decr_hits 0
    STAT cas_misses 0
    STAT cas_hits 0
    STAT cas_badval 0
    STAT auth_cmds 0
    STAT auth_errors 0
    STAT bytes_read 7
    STAT bytes_written 0
    STAT limit_maxbytes 134217728
    STAT accepting_conns 1
    STAT listen_disabled_num 0
    STAT threads 4
    STAT conn_yields 0
    STAT bytes 0
    STAT curr_items 0
    STAT total_items 0
    STAT evictions 0
    END
    
    quit

