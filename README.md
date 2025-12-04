# Project Outline: Github actions to docker deployment

This pipeline will trigger upon a push to you repository, but its job will be simply deploy the pre-existing image from Docker Hub to a target server.

## 1, Prerequisites & secret configuration
Create new SSH key specifically  for this deployment (do not usee your personal key)
- `ssh-keygen -t rsa -b 4096 -f deploy_key`
## 2. Add public key to deployment server
Add the contents of `deploy_key.pub` to the `~/ssh/authorized_keys` file on your target
## 3. Create github secrets
In your Github repository, go to the **Settings > Secrets and variables > Actions** and create the following repository secrets:
- `SSH_PRIVATE_KEY` 
- `DEPLOY_HOST`
- `DEPLOY_USER`
- `DOCKER_IMAGE`