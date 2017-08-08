# kubernetes-linuxacademy
This is for learning purposes kubernetes
# file:apache.yaml
 -$ kubectl get pod apache
 -$ kubectl describe pod apache
 -$ kubectl run busybox --image=busybox --restart=Never --tty -i --generator=run-pod/v1
 -$ wget -qO- http://$POD_IP
 -$ kubectl port-froward apche :80 & { It will forward to the localhost }
 -$ wget -qO- http://localhost:<$Mapping_port>
