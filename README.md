# Node-project-kube

![alt text](https://img.shields.io/docker/automated/timon02/node-replicas?style=for-the-badge)
![GitHub last commit](https://img.shields.io/github/last-commit/tikam02/Node-project-kube?style=for-the-badge)
*********
Stack - Node.js + Express.js + MongoDB + Docker + Kubernetes + Prometheus + Grafana

*****
- Node Project
- Docker and Dockerfile
- Docker Push
- Creating Kubernetes Cluster
- Setting Up Kubernetes on Machine
- Setting up and Deploying MongoDb
- Setting up main app and Deploying
- Installing Helm 
- Setting up Prometheus and Grafan with Helm  Charts
- Port forwarding Prometheus-manager,Grafana and Alertmanager to localhost
- Monitor Clusters and all architecture from localhost.


*********************

### Node Project 
For Running The web app locally:
```bash
$  cd /local/node
$ npm install
$ node app.js 
```




 





### Docker file and Dockerhub

```bash

For Running web App in Docker 

$ mv  /local/node  ~./home          //move node app to home directory because db setup at home for time to time restart.

$  docker build   -t  dockerhub-username/node-project .

 $ docker images  -a     //check for build image

 $ docker push username/repository:tag

 $ docker-compose up --build  

 $ Open --->  localhost:3000
 
 ```


### Getting Started With Kubernetes

For Running WebApp Clusters and Monitoring with Prometheus and Grafana


- Download cluster Config file from owner of cluster and connect to the cluster:
```
 $ cd ~/.kube && kubectl --kubeconfig="clustename-kubeconfig.yaml" get nodes
 ```

- Get kubectl nodes:
```
$ kubect get nodes
```

- Get pods:
```
    $ kubectl get pods 
```

- Get Services :
```
$ kubectl get services
```

- Get Deployments:
```
$ kubectl get services
```

- See MongoDb pods

```
$ kubectl exec -it mongo-mongodb-replicaset-0 -- mongo -u tikam -p --authenticationDatabase admin
```

- Port Forward Grafans to monitor in localhost:
```
$ kubectl port-forward -n monitoring svc/doks-cluster-monitoring-grafana 8000:80
```


- Port Forward Prometheus to monitor in localhost:
```
$  kubectl port-forward -n monitoring svc/doks-cluster-monitoring-pr-prometheus  9090:9090
```

- listing running Services in the monitoring namespace:
```
    $ kubectl get svc -n monitoring
 ```

- Deploying Spekt8 :

```
$ kubectl apply -f spekt8-deployment.yaml

$ kubectl apply -f fabric8-rbac.yaml.

$ kubectl port-forward deployment/spekt8 3000:3000

```



****************************************
![Node Web App](https://github.com/Tikam02/Node-project-kube/blob/master/images/frontend.png)

![Grafana](https://github.com/Tikam02/Node-project-kube/blob/master/images/grafana.png)

![Prometheus](https://github.com/Tikam02/Node-project-kube/blob/master/images/prometheus.png)

![Spekt8](https://github.com/Tikam02/Node-project-kube/blob/master/images/spek8.png)







