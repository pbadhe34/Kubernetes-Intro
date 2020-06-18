The PYthon app image pbadhe34/my-apps:app1 has been modified to 
look for the redis host on localhost machine.
This redis container deployed in the same POD is recognozed as redis runningn on localhost:6379 

kubectl get nodes

kubectl describe node docker-desktop

From /Pod-Localhost-Volume dir
kubectl create -f MySql-PersistentVoulme.yml

kubectl create -f MySql-PersistentVoulme-Claim.yml

kubectl get pv

kubectl get pvc

kubectl apply  -f user-app-pod-localhost-mysql.yml

kubectl create  -f user-app-pod-localhost-mysql.yml

kubectl get pod user-app-pod 

kubectl describe  pod user-app-pod

kubectl logs user-app-pod user-app


Do port forwarding with kubectl

 kubectl port-forward pod/user-app-pod 9090:8090

Open in browser  

http://localhost:9090/webapp-mysql/users/update 

http://localhost:9090/webapp-mysql/users/getUser/11

To post new data with post method

http://localhost:9090/webapp-mysql/users/add


kubectl logs user-app-pod mysql-localhost-container
 

kubectl exec -i -t user-app-pod  --container mysql-localhost-container  -- /bin/bash


kubectl exec --stdin --tty user-app-pod mysql-localhost-container  -- /bin/bash


kubectl exec user-app-pod mysql-localhost-container env

kubectl exec user-app-pod mysql-localhost-container -- ps aux
kubectl exec user-app-pod mysql-localhost-container -- ls /
kubectl exec user-app-pod mysql-localhost-container -- cat /proc/1/mounts




 



