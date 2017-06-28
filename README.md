# angular-spring-test
AngularJs to Spring Boot tests

# Redis controller
it needs a running Redis db

Redis support in spring data
http://docs.spring.io/spring-data/redis/docs/1.4.0.RC1/reference/html/redis.html


# Redis cheat sheet
List of commands here https://redis.io/commands

### Redis client
- redis-cli -h  192.168.99.100 -p 6379 - connect to a different machine and port


### General
KEYS * - shows all the keys
scan 0 MATCH word* COUNT 100 - returns the keys matching word*


### Hashes
hgetall <the key of the hash> - displays all 

### Transactions
&gt; MULTI  
OK  
&gt; INCR foo  
QUEUED  
&gt; INCR bar  
QUEUED  
&gt; EXEC  
1) (integer) 1  
2) (integer) 1  

WATCH is for optimistic locking. Watch is discarded after the transaction ends (EXEC or DISCARD)
 
### Ordered set
zrange <the key of the set> 0 -1 -displays the whole set ordered by rank
zrevrange 	- displays the values in reverse order


