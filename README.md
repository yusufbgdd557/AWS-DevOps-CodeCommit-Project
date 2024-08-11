
# AWS DevOps Project 2 : Cloud-Based Git Workflow on EC2

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
   - Connect to your EC2 instance via SSH using Visual Studio Code (due to access restrictions to Cloud9): For details more   [click here](https://github.com/yusufbgdd557/AWS-DevOps-Project-2/blob/master/EC2-SSH.md)

      ![2](https://github.com/user-attachments/assets/b2adebd3-7d83-47b9-b94f-8c81d48a90c0)

   
5. **Install Apache Maven and Amazon Corretto**
   - Install Maven and Amazon Corretto for Java development:
     ```bash
     sudo amazon-linux-extras enable corretto8
     sudo yum install -y java-1.8.0-amazon-corretto-devel
     ```
     
     ```bash
     sudo wget https://repos.fedorapeople.org/repos/dchen/apache-maven/epel-apache-maven.repo -O /etc/yum.repos.d/epel-apache-maven.repo
     sudo sed -i s/\$releasever/6/g /etc/yum.repos.d/epel-apache-maven.repo
     sudo yum install -y apache-maven
     ```

      ![3](https://github.com/user-attachments/assets/f4875817-b35b-4fb9-b137-232e8a6d8c58)

      
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
   - Create a new GitHub repository as an alternative to AWS CodeCommit. (I initially aimed to use CodeCommit, but due to new user restrictions, I was unable to access it. Therefore, I used GitHub to continue my development.)

9. **Connect Local Repository to Remote Repository**
   - Add the GitHub repository as a remote origin using a Personal Access Token (PAT):
   
     ```bash
     git remote add origin https://<PAT>@github.com/yusufbgdd557/yusufbgdd557-AWS-DevOps-CodeCommit-Project.git
     ```

 10. **Push Local Changes to GitHub**

      - **Add your files to the local repository:**
        ```shell
         git add .
        ```
     This command stages all changes in your project directory for the next commit.
   
      - **Commit the changes:**
         ```shell
         git commit -m "First commit"
         ```
     This command saves the staged changes to your local repository with a descriptive message.

      - **Push the changes to GitHub:**
        ```shell
          git push -u origin main
        ```
     This command uploads your local changes to the remote repository on GitHub and sets `main` as the default branch for future pushes.

        ![5](https://github.com/user-attachments/assets/445b0bd0-c5dd-4fea-b7c7-0630839c1e2f)

        ![6](https://github.com/user-attachments/assets/057fa088-6714-4a9a-9103-a4f983e17250)

        ![7](https://github.com/user-attachments/assets/0c4fffb8-bad3-4384-9a52-bd88d17a6123)
   
        ![8](https://github.com/user-attachments/assets/3f852c74-3130-4327-82d7-60c7a3e6552f)

## Conclusion

This project demonstrates setting up a Java development environment on AWS EC2, using Git and GitHub for version control. It serves as a practical alternative to AWS CodeCommit for managing code and resources in the cloud.

















