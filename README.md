
Requirments:
- Jenkins that is work
- AWS SDK
- Credentials binding plugin

In your jenkins, configure your AWS credentials.

We need to two piplines:
1. The Build proccess (Jenkinsfile):
   1. Pull the repository
   2. Build the image
   
- Run(Deploy)(Jenkinsfile.run):
  1. Job runs every 5 minutes because of the */5 * * * * configuration 
  2. Run the image from latest successful build named ci pipline