Installation :
#For Docker 

sudo apt install -y docker.io
sudo systemctl enable docker
sudo usermod -aG docker $USER

#For Kubectl
curl -LO "https://dl.k8s.io/release/$(curl -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
chmod +x kubectl
sudo mv kubectl /usr/local/bin/

#For minikube
curl -LO "https://dl.k8s.io/release/$(curl -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
chmod +x kubectl
sudo mv kubectl /usr/local/bin/

#Start Minikube with Docker Driver
minikube start --driver=docker

# Check the Pod
kubectl get pods

#Expose the Pod
kubectl expose pod nginx --type=NodePort --port=80

# To Check Everything is Running:
kubectl get nodes
