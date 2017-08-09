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
  
  
  
