### Preparation
1. Make sure your pc has installed with minikube and kubectl

### Create a minikube cluster
1. Run this command bellow <br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-13/image/img1.png"/></br>

### Open the Dashboard
1. Open new terminal and run <br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-13/image/img2.png"/></br>

### Create a Deployment
1. Use the kubectl create command to create a Deployment that manages a Pod. The Pod runs a Container based on the provided Docker image. <br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-13/image/img3.png"/></br>
2. View the Deployment: <br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-13/image/img4.png"/></br>
3. View the Pod: <br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-13/image/img5.png"/></br>
4. View cluster events:<br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-13/image/img6.png"/></br>
5. View the kubectl configuration:<br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-13/image/img7.png"/></br>

### Create a Service
1. Expose the Pod to the public internet using the kubectl expose command: <br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-13/image/img8.png"/></br>
2. View the Service you created: <br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-13/image/img9.png"/></br>
3. Run the following command: <br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-13/image/img10.png"/></br>

### Enable addons
1. List the currently supported addons:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-13/image/addons-output.png"/></br>
2. View the Pod and Service you created by installing that addon:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-13/image/addons-output.png"/></br>

### Clean up
1. Now you can clean up the resources you created in your cluster:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-13/image/cleanup-kubectl-delete-deploy.png"/></br>
2. Stop the Minikube cluster</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-13/image/cleanup-kubectl-stop.png"/></br>