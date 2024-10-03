<h1>Super Mario Game Deployment on EKS clusters</h1>
courtesy of Aakib -->https://aakibkhan1.medium.com/project-6-deployment-of-super-mario-on-kubernetes-using-terraform-74c7ce79b1f6

I played this game as a teenager. Yes I have been around for a while and to have
But it was so gratifying playing it again bit

![image](https://github.com/user-attachments/assets/84232888-e5e9-4325-8a0b-213d67930688)

To get this game rolling, you need an AWS account or one with a cloud provider but I did this on AWS

1. Launch an EC2 Instance. I went for a free tier Ubuntu 22.04 and I opened ports for HTTPS http and SSH
2. I connected to the instance and set up the docker, AWS CLI, terraform, and kubectl environment.
3. Then I created a role, gave it admin access, and attached the role to the instance.
4. I built the infra with Terraform. (Yes we want to automate because there are a couple of resources created so it is easy to clean up)
5. Then I created the deployment and the service for EKS
6. I played and screamed like a mad teen lol.....only joyful
7. i created an image for the instance because i wanted to play this game again.....Don't judge me.

