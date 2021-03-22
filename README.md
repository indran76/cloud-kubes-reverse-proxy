# cloud-kubes-reverse-proxy
Kubernetes and Reverse Proxy

__Test Pods__
1. Deploy 
```
$ kubectl apply -f deploy/deployment.yaml
```
2. Deploy services
```
$ kubectl apply -f deploy/service.yaml
```

3. Get pods
$ kubectl get pods
```
NAME                            READY   STATUS    RESTARTS   AGE
my-app-2-58fc655f9d-8zkww       1/1     Running   0          21m
reverseproxy-58679d7d44-vvf2f   1/1     Running   0          10m
(base)
```
4.  kubectl exec -it reverseproxy-58679d7d44-vvf2f bash

```
root@my-app-2-58fc655f9d-8zkww:/usr/src/app# curl http://my-app-2-svc:8080/health
Hello!root@my-app-2-58fc655f9d-8zkww:/usr/src/app# exit
```

5.
```
$ kubectl delete deployment  my-app-2
deployment.apps "my-app-2" deleted
(base)
mcroos@INDRAN-I6700K:~/code/cloud-simple-express
$ kubectl delete deployment reverseproxy
deployment.apps "reverseproxy" deleted
(base)
```
