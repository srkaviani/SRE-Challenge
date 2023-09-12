# SRE Challenge

## _Network Architecture_
![](https://raw.githubusercontent.com/srkaviani/SRE-Challenge/master/arch1.PNG)

## Details

- All Servers have an internal network interface
- LoadBalancer Server also have a public network interface that Receives User Requests and Loadbalance traffics between different nodes for Database and Web. 
- In addition SSH Server has a Floating IP Address to be accessible from everywhere.
- There are 3 Webservers that acts as Webserver with nginx service and also they are mariadb galera nodes.
- Opensearch Cluster and logstash are deployed on ssh server for managing webserver logs.
- There are a high available ceph cluster on 3 nodes (each node is mon and osd)
- CephFS Used to share application data path (/var/www/html) in all webservers.
- Some tuning for linux and nginx applied on webservers.
