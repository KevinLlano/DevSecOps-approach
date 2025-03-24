# DevSecOps-approach 🚀  

## 1. Project Overview  
**Project Overview:**
The purpose of this project is to implement a DevSecOps pipeline for securing a frontend application. It involves setting up a Jenkins pipeline that integrates various tools like SonarQube, Trivy, OWASP, and others. This ensures code quality, testing, security, and compliance are maintained throughout the development lifecycle. 

**Problem Solved:**
The project addresses the need for automated security, compliance, and quality checks in the software development process, reducing vulnerabilities and ensuring robust, secure application deployments.

## 2. Tools & Technologies Used 🛠  

- **Version Control:** Git, GitHub  
- **CI/CD:** Jenkins  
- **Infrastructure as Code:** Terraform  
- **Cloud:** AWS (EC2, AIM, App Deployment)  
- **Containerization & Orchestration:** Docker  
- **Security & Scanning:** SonarQube, Trivy (Image & File System), OWASP Dependency-Check (DP)  
- **Monitoring & Logging:** CloudWatch
- **Code Quality & Static Analysis:** SonarQube (Quality Gates)  
- **Package Management:** NPM  
- **Deployment & Automation:** Amazon EC2, Jenkins Pipeline  


## 3. Step-by-Step Implementation 🚀  

Got it! Here's the revised version with everything included in the steps, without separating them into distinct sections:

---

### EC2 Setup and Jenkins Pipeline Configuration 🏗

1. Created an IAM user named Jenkins and retrieved its access key.  
2. Ran the command `aws configure` on the VS IDE, entered the access key and secret access key, and set the default region and format options.  
3. Launched an EC2 instance using Terraform by configuring the security group, cloud provider, listing inbound and outbound ports, and setting up the VM environment to "Large."  
4. Installed required Jenkins plugins: Node.js, Docker, OWASP, and Java/Temurin.  
5. Installed necessary tools for the plugins, such as Adoptium.net and SonarQube.  
6. Created an IAM user named Jenkins from the IAM role with administrative access.  
7. Generated an access key/secret access key for the IAM Jenkins user.  
8. Downloaded the GitHub folder called `JENKINS-TF` containing Terraform files to install Jenkins, Docker, Trivy, and SonarQube, and ran it on VS Code.  
9. Ran `aws configure` in the terminal and entered the access key ID and secret access key when prompted. Set the region to Virginia and the output format to JSON.  
10. Executed `terraform init`, followed by `terraform validate` to validate the configuration, then ran `terraform plan` to ensure the configurations were correct. Finally, applied the configuration with `terraform apply`.  
11. Verified the EC2 instance was created successfully in the AWS Console.  
12. Copied the Public IPv4 address from the AWS Console and pasted it into the browser with `:8080` to launch Jenkins.  
13. Set up a SonarQube server within the Jenkins system.  
14. Created a new Jenkins pipeline using Node.js 18 and JDK 17 for testing, which will later integrate the frontend GitHub repository.  
15. Created the pipeline with Git using the repository `https://github.com/KevinLlano/DevSecOps-approach.git`.  
16. Integrated SonarQube testing into the Jenkins pipeline through pipeline syntax, enhancing the previously created GitHub pipeline.  
17. Created a SonarQube project within the "Projects" section of SonarQube and inserted the generated token.  
18. Added containerization with Docker by setting up an image and deploying the Amazon clone app on port 3000.

---

## CHALLENGES

Here's a more polished version of the challenges section:

---

### Challenges

1. Encountered issues with the secret access key, as the one I initially entered was being read incorrectly. I resolved this by generating a new access key.  
2. Faced difficulties with matching key pairs, as the configuration was not working properly.  
3. Had to run the command `python3 -m git_filter_repo --path JENKINS-TF/.terraform/providers/registry.terraform.io/hashicorp/aws/5.88.0/windows_amd64/terraform-provider-aws_v5.88.0_x5.exe --invert-paths --force` to remove the history for an `.exe` file that was too large.  
4. The remote repository was somehow removed without any indication or error message. After some analysis, I identified that the repo needed to be added again to resolve the issue of zero commit additions.  
5. Struggled to find the OWASP Dependency Check through documentation, as it was difficult to locate. It was only visible within the script code, making it hard to track.

---

## SCREENSHOTS

![Cloud Diagram](CloudArchitectureDiagram.png)
![Pipeline Stages](pipelineStasges-1.png)
![Script](pipelineScript.png)
![OWASP](OwaspMonitoring.png)
![SonarQube Monitoring](SonarQubeMonitoring.png)
![EC2 Instance](EC2instance.png)
![Build Success](Jenkins#15build.png)
![Deployed App](amazondeploy1.png)