# kubernetes-linuxacademy
This is for learning purposes kubernetes
# file:apache.yaml

  -$ kubectl get pod apache
  
  -$ kubectl describe pod apache
  
  -$ kubectl run busybox --image=busybox --restart=Never --tty -i --generator=run-pod/v1
  
  -$ wget -qO- http://$POD_IP
  
  -$ kubectl port-forward apche :80 & { It will forward to the localhost }
  
  -$ wget -qO- http://localhost:<$Mapping_port>
  
# file:nginx-pod-label.yaml

  -$ kubectl create -f nginx-pod-label.yaml
  
  -$ kubectl get pods -l app=nginx
  
  -$ kubectl describe pods -l app-nginx
  
# file:nginx-deployment-dev.yaml

  -$ kubectl create -f nginx-deployment-dev.yaml
  
  -$ kubectl get pods
  
  -$ kubectl describe deployments
  
  -$ kubectl describe deployments -l app=nginx-deployment-dev
  
  -{ If we want to change the version in dev environment where we need to update the version of nginx } 
    
  -$ kubectl apply -f nginx-deployment-update-dev.yaml
  
# file:nginx-multi-label.yaml
  
  -$ kubectl create -f nginx-multi-label.yaml
  
  -$ kubectl get pods
  
  -$ kubectl describe pods
  
  -$ kubectl describe replication controller
  
    If we try to delete any pod the replication controller will try to bring it back

# file:nginx-service.yaml

 -$ kubectl create -f nginx-service.yaml
 
 -$ kubectl get service 
 
 -$ kubectl describe service nginx-service
 
 -$ kubectl run busybox --image=busybox --restart=Never --tty -i --generator=run-pod/v1
 
 -$ wget -qO- http://$CLUSTER_IP:8000
 
 -$ kubectl delete service nginx-service
 
# Creating Temporary pods at the command line

 -$ kubectl run mysample --image=latest123/apache 
 
 -$ kubectl get pods
 
 -$ kubectl get deployments
 
 -$ kubectl describe deployments 
 
 -$ kubectl describe pod <running pod>
 
 -$ kubectl delete deployment mysample
 
 -$ kubectl get deployments { It will not show anything }
 
 -$ kubectl get pods
 
  For replicas to run in the command line 
  
  -$ kubectl run myreplicas --image=latest123/apache --replicas=2 --labels=app=myapache,version=1.0
  
  -$ kubectl describe deployment myreplicas
  
  -$ kubectl get pods
  
  -$ kubectl describe pods -l version=1.0
  
  #Interacting with Pod Containers
  
  -$ kubectl exec apache date
  
  -$ kubectl exec apache -i -t -- /bin/bash
  
  -root@apache:/# ps aux | grep apache
    -export TERM=xterm
    -apt-get update
    -apt-get install lynx
    -lynx http://localhost
    -mv index.html index.backup
    -echo "This is a test page" > index.html
    -lynx http://localhost
    - exit
    
  -$ kubectl get pods { The pod will be running }
  
  -$ kubectl exec myapache -i -t -- /bin/bash
  
  -$ lynx http://localhost
     - xterm
