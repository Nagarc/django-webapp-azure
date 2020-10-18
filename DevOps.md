## 1. Clone the repository
 
git clone https://github.com/Nagarc/notejam.git
 
Push the repository to to azure devops and  We can achieve this in multiple
ways. create empty repo and push or import repo from cloned repo or directly from Git to Azure repos.
 
Pending - containerizing .
 
for simplicity, if you have already image created in local, use below command
 
cd notejam/django
 
az acr build --registry njdcr --image notejam1
 
 
## 2. Continuous Build:
 
az acr task create --registry njdcr --name webapp --image notejam1  --context <url of azure devops repo > --branch master --file Dockerfile
 
## 3. Continuous deployment
 
Configure continuous deployment and create a webhook
 
   Go to Azure portal 
   Go to the Container settings page of the web app
 
   Set Continuous Deployment to On,
   and then select Save.
  
This setting configures a webhook that Container Registry uses to alert the web app that the Docker image has changed. This ACR Task will be hooked to this repo to generate the build
of an image automatically. ACR tasks can be created to generate the image.
 

