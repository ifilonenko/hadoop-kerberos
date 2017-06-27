### Bloomberg Big Data and NoSQL Platform
#### 1. Configure Docker networking

Hadoop requires reverse DNS.  Under docker-compose, we require an external network named "com" for hosts to resolve forward and backwards.

```
docker network create com
```

#### 2. Download a distro of Hadoop 


#### 3. Start it up

```
docker volume rm hadoopkerberos_server-keytab
docker-compose up -d --force-recreate --build
```

#### 4. Run HDFS commands

```
docker exec -it nn.example /bin/bash
kinit -kt /var/keytabs/hdfs.keytab hdfs/nn.example.com
hdfs dfs -ls
```






