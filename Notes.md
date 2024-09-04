# [Link](https://youtu.be/KAa2l0oycOk?t=979)

## Status

Not working. Same 404 error.

## Commands

### Configure Cluster

> Create civo cluster \
> `$ civo kubernetes create saiyam-certmgr --size "g4s.kube.medium" --nodes 2 --wait --save --merge --region FRA1`

> Show details of cluster \
> `$ civo kubernetes show saiyam-certmgr`

> Get DNS A Name \
> `$ export CLUSTER_DNS=$(civo kubernetes show saiyam-certmgr | grep 'DNS A record' | xargs | awk -F' : ' '{print $2}')` \
> `$ echo $CLUSTER_DNS`

### Install Ingress Controller

> Install cert-manager \
> `$ kubectl apply -f https://github.com/cert-manager/cert-manager/releases/download/v1.11.0/cert-manager.yaml`

> Get Saiyam repo \
> `$ git clone https://github.com/saiyam1814/kube-certs.git`

### Configure Cluster

> Create namespace demo \
> `$ kcrns demo`

> Install nginx controller \
> `$ export version=controller-v1.6.3` \
> `$ kaf https://raw.githubusercontent.com/kubernetes/ingress-nginx/$version/deploy/static/provider/cloud/deploy.yaml`

### Apply deployment

> `$ envsubst < ./kube-certs/deploy/deploy.yaml | kubectl apply -f -`
