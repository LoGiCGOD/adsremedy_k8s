# adsremedy_k8s

The deployment files are inside k8s_manifests folder

cd inside it and run the following command to deploy-
 1) kubectl apply -f api-deployment.yaml
 2) kubectl apply -f api-service.yaml
 3) kubectl apply -f hpa_api.yaml (This is for autoscaling the pods)

Run the command- 
1) minikube ip (to get the minikube ip)
2) kubectl get svc (to get the port no. Since the service type is Nodeport.)

Once deployed stress the api using hey. Use the command-
1) hey -n 3000 -c 100 http://192.168.49.2:31100 (change the ip and port base on your machine)
2) kubectl get pods (to check if pods are incremented)
3) kubectl get hpa (to monitor the targets)



**Application video link and screenshots**
https://drive.google.com/drive/folders/18N9_TxhUU6cLCaeQ0BSkLFo85kCPgjrM?usp=drive_link
