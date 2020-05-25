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