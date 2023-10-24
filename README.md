# 3.5assignment

Step-by-step how to create an image until it will be deployed to AWS ECR
Step 1: Create ECR Repo on AWS. Note the URI (255945442255.dkr.ecr.us-east-1.amazonaws.com/zmw-ecr-repoabc)
Step 2: Build docker image with command and tag it as latest: docker build -t 23octzmw:latest .  
Step 3: Create a tag target image (ECR) that refers to the source image (local) with the command: docker tag 23octzmw:latest 255945442255.dkr.ecr.us-east-1.amazonaws.com/zmw-ecr-repoabc:latest
Step 4: Log in to AWS ECR with the command: aws ecr get-login-password --region us-east-1|docker login --username AWS --password-stdin 255945442255.dkr.ecr.us-east-1.amazonaws.com
Step 5: Push image into ECR with the following command: docker push 255945442255.dkr.ecr.us-east-1.amazonaws.com/zmw-ecr-repoabc:latest
