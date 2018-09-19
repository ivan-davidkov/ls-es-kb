# logstash elasticsearch kibana 

all in one solution

(eleasticsearch)[http://localhost:9200]
(eleasticsearch)[http://localhost:9300]
(kibana)[http://localhost:5601]
(logstash)[tcp://localhost:5044] 
(logstash)[http://localhost:5555] 

these folders are shared b/w all containers
```sh
data/
├── input
└── output
```

boot up all containers in background
```sh
$>docker-compose -f docker-compose.yaml up -d
```

check if containers are running
```sh
$>docker-compose -f docker-compose.yaml ps
    Name                   Command               State                    Ports                 
------------------------------------------------------------------------------------------------
elasticsearch   /usr/local/bin/docker-entr ...   Up      0.0.0.0:9200->9200/tcp,                
                                                         0.0.0.0:9300->9300/tcp                 
kibana          /bin/bash /usr/local/bin/k ...   Up      0.0.0.0:5601->5601/tcp                 
logstash        /usr/local/bin/docker-entr ...   Up      0.0.0.0:5044->5044/tcp,                
                                                         0.0.0.0:5555->5555/tcp, 9600/tcp 
```

stop all containers
```sh
$>docker-compose -f docker-compose.yaml down
```

