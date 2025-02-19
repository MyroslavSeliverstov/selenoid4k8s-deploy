# selenoid4k8s kubernetes deployment

kubectl client should be installed and pointing to the cluster

## Clone repository

```
$ git clone https://github.com/alcounit/selenoid4k8s-deploy.git
$ cd selenoid4k8s-deploy
```

## Create namespace

```
$ kubectl apply -f 01-selenoid-namespace-role.yaml
```

## Create configmap with browsers config

```
$ kubectl apply -f 02-selenoid-configmap.yaml
```

## Create nodePort

```
$ kubectl apply -f 03-selenoid-nodeport.yaml
```

## Deploy selenoi4k8s to kubernetes

```
$ kubectl apply -f 04-selenoid-deployment.yaml
```

## Pull all images listed in configmap

```
$ kubectl apply -f 05-selenoid-prepull-deamonset.yaml
```

Run your tests by using any node ip/name and port 30001

```
http://node01:30001/wd/hub
```

selenoid-ui accessible on nodeport 30002

```
http://node01:30002/
```
