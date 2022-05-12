## Comandos Kubernetes para aplicacion microservicios mongodb/mongo-express

**Crea el cluster con minikube**
- minikube start --driver=hyperv

**Crea el configmap**
- kubectl apply -f mongo-configmap.yml

**Crea los secrets**
- kubectl apply -f mongo-secret.yml

**Crea el persistentVolumeClaim del backend**
- kubectl apply -f mongodb-pvc.yml

**Crea el presistentVolumeClaim del frontend**
- kubectl apply -f mongo-express-pvc.yml

**Crea el deployment del backend y el servicio clusterIP**
- kubectl apply -f mongodb-deployment.yml

**Crea el deployment del front end y el servicio LoadBalancer con Minikube**
- kubectl apply -f mongo-express-deployment.yml

**Exponer el frontend al publico con minikube**
- minikube service mongo-express-service --url

**hacer rollout de la aplicacion**
- kubectl rollout undo deployment mongo-express
