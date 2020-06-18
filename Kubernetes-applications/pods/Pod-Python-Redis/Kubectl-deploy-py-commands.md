The PYthon app image pbadhe34/my-apps:app1 has been modified to 
look for the redis host on localhost machine.
This redis container deployed in the same POD is recognozed as redis runningn on localhost:6379 

kubectl get nodes

kubectl describe node docker-desktop

From /python app dir

 
kubectl apply  -f Py-redis-localhost.yml

 

kubectl get pod pod-py-redis

kubectl get pod pod-py-redis -o wide


kubectl describe pod pod-py-redis

kubectl logs  pod-py-redis

kubectl port-forward pod/pod-py-redis 8090

kubectl port-forward pod/pod-py-redis 9090:8090


 
kubectl delete  -f Py-redis-localhost.yml


 


 



