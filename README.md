# 3.5assignment
## _Cloud Native Application - Containerization II_


**Step-by-step on how to create an image until it is deployed to AWS ECR**

- Step 1 : Create ECR Repo on AWS. Repo created as 255945442255.dkr.ecr.us-east-1.amazonaws.com/zmw-ecr-repoabc

- Step 2: Build docker image with command and tag it as latest
```sh
docker build -t 23octzmw:latest
```

- Step 3: Create a tag target image (ECR) that refers to the source image (local) with the command
```sh
docker tag 23octzmw:latest 255945442255.dkr.ecr.us-east-1.amazonaws.com/zmw-ecr-repoabc:latest
``` 

-Step 4: Log in to AWS ECR with the command
```sh
aws ecr get-login-password --region us-east-1|docker login --username AWS --password-stdin 255945442255.dkr.ecr.us-east-1.amazonaws.com
```

-Step 5:  Push image into ECR with the following command
```sh
docker push 255945442255.dkr.ecr.us-east-1.amazonaws.com/zmw-ecr-repoabc:latest
```
