The PYthon app image pbadhe34/my-apps:app1 has been modified to 
look for the redis host on localhost machine.
This redis container deployed in the same POD is recognozed as redis runningn on localhost:6379 


kubectl api-resources

kubectl get nodes

kubectl describe node docker-desktop

From /Pod-Localhost-Volume dir

 
kubectl apply  -f hostNetwork-WebApp.yml

kubectl create  -f hostNetwork-WebApp.yml

kubectl get pod webpod

kubectl get pod webpod -o wide

In watch mode
kubectl get pods -w


kubectl describe pod webpod

kubectl logs  webpod

kubectl get pods webnw-pod -o jsonpath='{.spec.containers[*].name}


On localhost address port mapping
kubectl port-forward pod/webpod 9090

On all addresses

 kubectl port-forward --address 0.0.0.0 pod/webpod 9090
 kubectl port-forward --address 0.0.0.0 pod/webpod 8090:9090
kubectl port-forward --address 0.0.0.0 pod/webapp-pod 9090
kubectl port-forward --address 0.0.0.0 pod/webapp-pod 8090:9090
kubectl port-forward --address 0.0.0.0 pod/webpod 1090

kubectl get namespaces 
kubectl create -f  NameSpaceAccounting.json
kubectl create  -f pod-DynamicNames-WebApp.yml

kubectl get pods 
kubectl get pods -n banking
kubectl get pods -n kube-system

kubectl get pods --all-namespaces

kubectl get pod my-pod -o yaml   


http://localhost:9090/webapp/info
http://192.168.1.207:9090/webapp/info


kubectl delete  -f hostNetwork-WebApp.yml


kubectl delete --all pods 

kubectl delete --all pods --namespace=foo


kubectl delete pod,service baz foo                                        # Delete pods and services with same names "baz" and "foo"
kubectl delete pods,services -l name=myLabel   

kubectl api-resources --namespaced=true      

kubectl api-resources --namespaced=false    
 # All non-namespaced resources

kubectl api-resources -o name  
       
       # All resources with simple output (just the resource name)

kubectl api-resources -o wide    
            # All resources with expanded (aka "wide") output

kubectl api-resources --verbs=list,get       
# All resources that support the "list" and "get" request verbs

kubectl api-resources --api-group=extensions #
 
##All resources in the "extensions" API group


kubectl delete --all namespaces
