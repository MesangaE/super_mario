<h1>Super Mario Game Deployment on EKS clusters</h1>

courtesy of Aakib -->https://aakibkhan1.medium.com/project-6-deployment-of-super-mario-on-kubernetes-using-terraform-74c7ce79b1f6




I played this game as a teenager. Yes I have been around for a while and to have
But it was so gratifying playing it again a bit

![image](https://github.com/user-attachments/assets/84232888-e5e9-4325-8a0b-213d67930688)

To get this game rolling, you need an AWS account or one with a cloud provider but I did this on AWS

1. Launch an EC2 Instance. I went for a free tier Ubuntu 22.04 and I opened ports for HTTPS http and SSH
2. I connected to the instance and set up the docker, AWS CLI, terraform, and kubectl environment then I cloned the repo my repo since I had made modifications to parts of the code so it could work in my environment (like changing regions in the provider.tf, the backend bucket name for the state file etc.) git clone https://github.com/MesangaE/super_mario.git
3. Then I created a role, gave it admin access, and attached the role to the instance.
4. I built the infra with Terraform. (Yes we want to automate because there are a couple of resources created so it is easy to clean up)
5. Then I created the deployment and the service for EKS
6. I played and screamed like a mad teen lol.....only joyful
7. I created an image for the instance because I wanted to play this game again.....Don't judge me.

<h2>creating the EKS infra</h2>h2>

Super Mario Bucket (backend) to store state files

![mario bucket](https://github.com/user-attachments/assets/4c46f431-fa19-4197-8c75-2db4f566117c)

![state files](https://github.com/user-attachments/assets/5eb3151c-f002-4044-a1c5-6cae4486b074)


<h2>Mario IAM role</h2>


![mario role](https://github.com/user-attachments/assets/e465f67e-ac28-41aa-9ea8-1d389e5ba435)

<h3>terraform init</h3>
![t init](https://github.com/user-attachments/assets/68a12595-878f-463d-942b-d31d57789868)

<h3>terraform plan</h3>
![t plan](https://github.com/user-attachments/assets/bd157148-2529-42fc-b6ce-13cb76887b00)

<h3>terraform apply</h3>h3>

![t apply](https://github.com/user-attachments/assets/4d10e739-7839-432f-931b-f43aac72ef3f)


<h3>node group</h3>
![node-group](https://github.com/user-attachments/assets/0d94a4c1-147a-4344-9ae1-2317bd6ce32a)

<h3>loadbalancer</h3>

![loadbalancer](https://github.com/user-attachments/assets/196f29e0-9b45-4cb6-bf1a-8b2546f3c85a)



![eksclusters](https://github.com/user-attachments/assets/989f3529-154a-4612-8a9e-325dd45c9619)


![created cluster](https://github.com/user-attachments/assets/4c850b41-c151-4842-8b8c-6760adecc5db)

<h3>created deployment and service</h3>

![kservice created](https://github.com/user-attachments/assets/e5c4bd05-92a3-40e9-b8bc-a9a5a28dec36)


load balancer ingress to paste into your browser
![kget all](https://github.com/user-attachments/assets/a6dcd4f7-c6eb-42bc-9e51-966603b3899e)

![deployment](https://github.com/user-attachments/assets/32037920-ed91-43e3-8577-66fd6d97fa03)

I created an image of my instance so I don't need to go through all the preceding steps. Rather I would re-apply my infra, create the deployments and the service then, boom! I am playing the game in less time

![image creation](https://github.com/user-attachments/assets/d1ae6c51-a038-4c14-85e3-41a0770f84b1)


![mario image](https://github.com/user-attachments/assets/5a3a32d2-06b2-4df8-a0a3-76cf57213125)




