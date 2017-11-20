# hdp-cluster for test
hadoop cluster for test - Hortonworks HDP 2.6 - ambari-hive-spark-YARN

Steps:
1. Dockerfile to create master node
2. Dockerfile to create data nodes, to scale hadoop cluster - replicate date nodes
3. Volume to retain testdata, use host dir

4. docker-compose -f compose/multinode.yml build

5. Bring up masternode, datanode:
    docker-compose -f compose/multinode.yml up
    
6. Deploy services (HDFS, YARN, Hive Spark) manually or via blueprint

7. Cluster is ready for test, connect to nodes for testing
    #find containers
    docker ps -a    
    docker exec -it <containerID> /bin/bash    
    
8. Start/stop cluster
    docker-compose -f compose/multinode.yml start/stop  
9. To remove cluster:
    docker-compose -f compose/multinode.yml down

Next:
To create docker cluster with Cloudera, MapR distributions of hadoop - with a goal to view test spark applications & view resource utilization, spark UI, YARN logs from cluster.
