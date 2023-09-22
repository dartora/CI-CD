# Portfolio CI/CD Pipeline

## Introduction
Welcome to  one project of my portfolio! This example shows the Continuous Integration and Continuous Deployment (CI/CD) pipeline setup using GitHub Actions and an AWS EC2 instance to automate the deployment of my web applications.

## AWS EC2
I utilize a simple AWS EC2 machine to host my web applications, which run on the Nginx web server.

## Pipeline Workflow
1. **Trigger**: This pipeline is triggered automatically after a push to the `main` branch in this repository.

2. **EC2 Verification**:
   - The pipeline starts by connecting to the designated EC2 instance.
   - It checks if the `/home/CI-CD` directory exists on the EC2 machine.
   - If the directory doesn't exist, the pipeline script clones the repository into it.
   - If the directory already exists, the script changes to that directory and performs a `git pull` to update the code.

3. **Deployment**:
   - After updating the code, the script deletes the contents of the `/var/html/*` directory on the EC2 instance, ensuring a clean slate.
   - It then copies the content from this CI/CD pipeline directory to the root directory of the Nginx web server, typically located at `/var/html`.

## Conclusion
With this CI/CD pipeline in place, my web applications are automatically deployed and updated on the EC2 instance whenever changes are pushed to the `main` branch in this repository. This automation streamlines the deployment process, ensuring that my portfolio is always up-to-date and accessible.

Feel free to explore my portfolio and check out my projects!
