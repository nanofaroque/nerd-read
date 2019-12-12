# Helper materials for course
* Log generator source : wget http://media.sundog-soft.com/AWSBigData/LogGenerator.zip

- Create a log directory to keep generated log data
``sudo mkdir /var/log/cadabra``
* To generate the log
``sudo ./LogGenerator.py 500000``

Kinesis Stream: 
1MB write/pershard
1000 write/second
2MB read/shard
It can be improved by using enhancing
 