Steps to solution:

1. Created a Dockerfile from the nginx image with a custom static content returned -> see related Dockerfile, index.html.

2. Installed a single node kubernetes cluster architecture using kubeadm on AWS EC2 instances.
3. Deployed a simple nginx app on my kubernetes cluster -> see related nginx-deployment.yaml file.

4. Created a LoadBalance type Service that balances over the newly created pod, using the lable app:nginx -> see related nginx-service.yaml file.
5. Now the docker container is exposed to the cluster's external IP using the service I have just created.

** I chose to use the declarative way of deploying and creating a Service just as a best practice.
    I am aware of the fact that I could have used the simple imperative way instead (deploy/expose commands in the CLI).


