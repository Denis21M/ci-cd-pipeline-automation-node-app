# simple-node-app

Steps to build a pipeline of a node project that creates and publishes a docker image and deploys it in an EKS cluster.

# To Setup the App

1. Create the node file
2. Run `npm init -y`
3. Ensure npm start works
4. Create the Dockerfile
5. Create the Kubernetes Deployment + Service

# To Enable the Workflow

1. Make sure your GitHub Repository is updated with your local code
2. Add Repo Secrets in Settings > Secrets and Variables > Actions:
    - DOCKER_USERNAME
    - DOCKER_PASSWORD
    - AWS_ACCESS_KEY_ID
    - AWS_SECRET_ACCESS_KEY
    - AWS_REGION
    - AWS_CLUSTER (your eks cluster name)
3. Review the steps of your workflow:
    - Checkout Code
    - Docker Login (with secret credentials)
    - Docker Build
    - Docker Push
    - Configure AWS (with secret credentials)
    - Replace the "image" variable in the k8s template
    - Install kubectl
    - Apply the deployment + service
4. Build the workflow
5. Test the workflow and fix errors