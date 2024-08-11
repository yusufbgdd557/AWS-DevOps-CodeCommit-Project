
# AWS DevOps Project 2

## Overview

This project involves setting up a Java web application on an AWS EC2 instance. It showcases the process of creating an EC2 environment, installing necessary tools, and using Git and GitHub for version control.

## Steps

1. **Create IAM User**
   - Create an IAM user in AWS with appropriate permissions.

2. **Create EC2 Instance**
   - Launch a new EC2 instance and download the `.pem` file for SSH access.

3. **Set Permissions for `.pem` File**
   - Set the permissions of the `.pem` file using the following command:
     ```bash
     icacls "C:\path\to\your\file.pem" /grant:r %username%:R
     ```
      ![1](https://github.com/user-attachments/assets/ecce2cf2-844b-4001-bee2-9d037cd0ea9e)


4. **Connect to EC2 Instance**
   - Connect to your EC2 instance via SSH using Visual Studio Code (due to access restrictions to Cloud9):
     ```bash
     ssh -i <path-to-your-pem-file> ec2-user@<your-ec2-public-dns>
     ```

5. **Install Apache Maven and Amazon Corretto**
   - Install Maven and Amazon Corretto for Java development:
     ```bash
     sudo yum install maven
     sudo yum install java-<version>-amazon-corretto
     ```

6. **Create Application Structure**
   - Generate the basic structure and packages for your Java application using Maven:
     ```bash
     mvn archetype:generate -DgroupId=com.example -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
     ```

7. **Initialize Local Git Repository**
   - Install Git, then create a local repository:
     ```bash
     sudo yum install git
     git init -b main
     ```

8. **Create GitHub Repository**
   - Create a new GitHub repository as an alternative to AWS CodeCommit.

9. **Connect Local Repo to Remote Repo**
   - Add the GitHub repository as a remote origin using a Personal Access Token (PAT):
     ```bash
     git remote add origin https://<PAT>@github.com/yusufbgdd557/yusufbgdd557-AWS-DevOps-CodeCommit-Project.git
     ```

10. **Push Local Changes to Remote Repo**
    - Add, commit, and push changes to the GitHub repository:
      ```bash
      git add .
      git commit -m "First commit"
      git push -u origin main
      ```

## Conclusion

This project demonstrates setting up a Java development environment on AWS EC2, using Git and GitHub for version control. It serves as a practical alternative to AWS CodeCommit for managing code and resources in the cloud.

---

Feel free to adjust any specific details as needed!
























# yusufbgdd557-AWS-DevOps-CodeCommit-Project

Permission for .pem
![1](https://github.com/user-attachments/assets/a45cc1eb-b47b-49af-aee5-9dd9be1b12e4)

connected to my ec2 instance
![image](https://github.com/user-attachments/assets/bda50a1b-6494-4a97-a1da-6e87c72e30e3)

downloaded apache maven and amazon coretto 
![image](https://github.com/user-attachments/assets/27fb368e-a3f5-4cb8-a999-ed9f0acab0fc)

created the application
![image](https://github.com/user-attachments/assets/d1b928ce-6dee-4d5b-91f9-240d043ab687)

