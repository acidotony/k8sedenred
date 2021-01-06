az aks update -n ear-dev-aks01-d-aks -g ear-dev-aks01-d-rg --attach-acr eardevacr01
kubectl create secret docker-registry regcred --docker-server=eardevacr01.azurecr.io --docker-username=eardevacr01 --docker-password=<passwordno"> --docker-email=antonio.machado@edenred.com
kubectl create namespace ingress-basic #create a namespace
kubectl apply -f deployment.yaml --namespace ingress-basic # create deployments on specific name space
kubectl get deployment --namespace ingress-basic # get deployments on specific name space
kubectl get events -n ingress-basic # events
kubectl create secret generic regcred --from-file=.dockerconfigjson=C:\Users\anmachado\.docker\config.json> --type=kubernetes.io/dockerconfigjson

# información del cluter
kubectl cluster-info 

# lista de los nodos del cluster
kubectl get nodes  

# lista de los servicios 
kubectl get service 

# lista de los pods
kubectl get pods   

# lista de deployments 
kubectl get deployments 

# lista de namespaces
kubectl get namespaces 

# lista de los pods del namespace prueba
kubectl get pods -n prueba  

# exponer un deployment
kubectl expose deployment first-deployment --port=80 --type=NodePort 

# información detallada del pod apache1 
kubectl describe pod apache1  

# eliminar servicio
kubectl delete service hello-world  

# eliminar deployment
kubectl delete deployment hello-world  

# escalar a 3 replicas un deployment
kubectl scale --replicas=3 deployment prestashop -n prestashop

# acceder al pod ubuntu-test  
kubectl --namespace=enmilocalfunciona exec -it ubuntu-test bash  

# crear un secret
kubectl create secret generic mysql-pass --from-literal=password=mypassword 

# aplicar el contenido del fichero deployment.yaml  
kubectl apply -f deployment.yaml 

# listar los tokens 
kubeadm token list  

# agregar nodo al cluster
kubeadm join --discovery-token-unsafe-skip-ca-verification --token=102952.1a7dd4cc8d1f4cc5 172.17.0.52:6443  


------- pendientes
Could not create a role assignment for ACR. Are you an Owner on this subscription?