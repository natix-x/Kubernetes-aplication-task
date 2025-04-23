# Kubernetes-application-task

 ```
   minikube start
   minikube mount C:\tmp\nfs:/mnt/nfs
   helm repo add stable https://charts.helm.sh/stable
   helm repo update
   helm install nfs-server-provisioner stable/nfs-server-provisioner `
  --set nfs.server.address=$(minikube ip) `
  --set nfs.server.path="/mnt/nfs" `
  --set storageClass.name="nfs-storage-class"
   kubectl apply -f pvc.yaml
   kubectl apply -f deployment.yaml
   kubectl apply -f service.yaml
   kubect apply -f jobs.yaml
   minikube service http-server-service
   ```