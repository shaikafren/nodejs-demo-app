This project is a simple **Node.js web app** that displays “Hello from Node.js App!”.  
It uses **GitHub Actions** for CI/CD to build and push a **Docker image** (`sana725/nodejs-demo-app`) to **Docker Hub**.  
The app is deployed on a **Kubernetes cluster** using `deployment.yaml` and `service.yaml`.  
After deployment, the app runs successfully and can be accessed through the cluster service.  
 # CI/CD build successful  
 # Docker image pushed to Docker Hub  
 # App deployed and verified on Kubernetes


 STEPS TO DEPLOY:
 1. Apply Deployment and Service files
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
2. Check if pods and services are running
kubectl get pods
kubectl get svc
3. exposed my application using k8s cluster 
 http://http://18.208.206.206:31058/

 full devops workflow end-to-end
 Code → Build (CI/CD) → Push to Docker Hub → Deploy to Kubernetes → Access the live app ✅
