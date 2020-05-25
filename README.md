# kubernetes
### Documentation 
https://kubernetes.io/docs/home/

###Create a new pod with the NGINX image
kubectl run nginx --image=nginx --generator=run-pod/v1

### Delete pod(s)
kubectl delete pods --all

kubectl delete pods pod_name

### Get pods
kubectl get pods

### Describe a particular pod 
kubectl describe pod pod_name

kubectl get pods -o wide 

### Create a new pod with the name 'redis123' and with the image 'redis123'
kubectl run redis --image=redis123 --generator=run-pod/v1

### Edit pods
kubectl edit pod pod_name

### Create pods using yaml file

apiVersion: batch/v1
kind: Job
metadata:
  name: hello
spec:
  template:
    # This is the pod template
    spec:
      containers:
      - name: hello
        image: busybox
      restartPolicy: OnFailure
      
kubectl create -f hello_pod.yaml

### Extract pod definition to yaml file and edit it.

If you are given a pod definition file, edit that file and use it to create a new pod. If you are not given a pod definition file, you may extract the definition to a file using the below command:

kubectl get pod <pod-name> -o yaml > pod-definition.yaml

Then edit the file to make the necessary changes, delete and re-create the pod.
Use the below command to edit pod properties.
 
kubectl edit pod <pod-name> 
    