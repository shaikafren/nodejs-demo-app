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
 http://18.208.206.206:31058/

 full devops workflow end-to-end
 Code → Build (CI/CD) → Push to Docker Hub → Deploy to Kubernetes → Access the live app ✅

INTERVIEW QUSETION AND ANSWERS AS MENTION IN THE TASK

1️.what is CI/CD?
A.CI/CD stands for Continuous Integration and Continuous Deployment.
CI builds and tests code automatically; CD deploys the latest version to production (like Kubernetes) automatically.

2️.How do GitHub Actions work?
A. GitHub Actions automate workflows.
When you push code, it runs a pipeline (YAML file) with jobs to build, test, and deploy your app.

3️.What are runners?
A. Runners are the virtual machines that execute your GitHub Action jobs.
Example: ubuntu-latest runner builds and runs your workflow steps.

4️.Difference between jobs and steps.
A. A job is a group of steps.
Steps are individual commands inside a job.
Example: one job = “build”; steps = “checkout”, “build Docker image”, “push image”.

5️.How to secure secrets in GitHub Actions?
A. Store them in GitHub → Settings → Secrets → Actions.
Use them as ${{ secrets.MY_SECRET }} in workflow files.
(Example: Docker Hub username & password)

6️.How to handle deployment errors?
A. Check logs from GitHub Actions and Kubernetes pods (kubectl logs).
Use retries, health checks, and proper rollback strategy in CI/CD.

7️.Explain the Docker build-push workflow.
A. In CI/CD:

Build image → docker build -t username/app:latest .

Login → docker login

Push → docker push username/app:latest
Then Kubernetes pulls that image for deployment.

8️.How can you test a CI/CD pipeline locally?
A. Use tools like act (for GitHub Actions)
or manually run build/test commands in a local Docker container before pushing to GitHub.
