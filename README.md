# Student Portal – CCA 2 CI/CD

A simple static website used to demonstrate a CI/CD pipeline with GitHub, Jenkins, Docker, Docker Hub, Minikube and Kubernetes.

## Before running the pipeline
1. Replace `YOUR_DOCKERHUB_USERNAME` in `Jenkinsfile` and `k8s/deployment.yaml` with your Docker Hub username.
2. Create a Docker Hub repository named `student-portal`.
3. Add a Jenkins username/password credential with ID `dockerhub-creds`; use your Docker Hub username and an access token.
4. Configure Jenkins to use this repository's `Jenkinsfile`.
5. Ensure the Jenkins process can use Docker and its own Minikube cluster.

## Pipeline stages
Checkout → Build and Test → Docker Build → Push Image → Deploy to Minikube → Verify Deployment.

The test stage verifies that the three application files exist. It is a basic file check, not a full browser-based test.

## Verification
Use `kubectl get pods`, `kubectl get deployments`, and `kubectl get services` under the same user/configuration that runs the Jenkins pipeline.

## Second deployment demonstration
Change the main heading in `index.html`, commit and push the change, then run the pipeline again. Verify the updated heading in the deployed website.

## Submission evidence
Add your GitHub URL and screenshots of the successful pipeline, Docker Hub image, Kubernetes resources, running website, and second deployment.
