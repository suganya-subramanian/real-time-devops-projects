# 🚀 CI/CD Pipeline using AWS CodePipeline, CodeBuild, and GitHub

This project demonstrates a complete **CI/CD pipeline on AWS**, integrating **GitHub**, **AWS CodePipeline**, and **CodeBuild** to automate the build and deployment process for a static website hosted on **Amazon S3**.

This is part of my **real-time DevOps projects practice** based on concepts learned from the **AWS Zero to Hero** course.

---

## 📌 Project Overview

| Item                 | Description                                                |
|----------------------|------------------------------------------------------------|
| **Project Title**    | CI/CD Pipeline in AWS                                      |
| **Purpose**          | Automate build & deployment of static website using AWS    |
| **CI Tool**          | AWS CodeBuild                                              |
| **CD Tool**          | AWS CodePipeline                                           |
| **Source Control**   | GitHub                                                     |
| **Deployment Target**| Amazon S3                                                  |
| **Hosting**          | AWS Console                                                |

---

## 🔄 CI/CD Workflow Explanation

1. ✅ **Source Stage**  
   - GitHub repo is connected to CodePipeline.
   - Any new push to the main branch triggers the pipeline automatically using webhooks.

2. 🛠️ **Build Stage**  
   - AWS CodeBuild uses `buildspec.yml` to install dependencies, build the project, and prepare the deployment artifacts.
   - Output is stored in an S3 bucket.

3. 🚀 **Deploy Stage**  
   - CodePipeline deploys the final output to the target S3 bucket.
   - The bucket is configured for static website hosting, so the application is served directly to users.

---

## 📸 Screenshot of CI/CD Pipeline

![CI/CD Architecture](https://github.com/suganya-subramanian/images/blob/main/Realtime%20project-CICD-using-AWSCodePipeline-AWSservices.png?raw=true)

---


## 🔗 Source Code Reference

- 🔹 **My Repository** (CI/CD Pipeline - Day 14):  
  [CI/CD Project - Suganya](https://github.com/suganya-subramanian/aws-devops-zero-to-hero/tree/main/day-14)

- 🔹 **Original Repository by Abhishek Veeramalla** (Day 14):  
  [CI/CD Project - Abhishek Sir](https://github.com/iam-veeramalla/aws-devops-zero-to-hero/tree/main/day-14)



🧠 Learnings & Skills Practiced

    Connected GitHub to CodePipeline via webhook triggers

    Wrote custom buildspec.yml for AWS CodeBuild

    Automated artifact deployment to Amazon S3

    Understood permissions with IAM roles for CI/CD services

    Practiced real-time DevOps setup on AWS console

🙏 Credits

Special thanks to Abhishek Veeramalla Sir for the YouTube series and inspiration. This project was practiced and implemented as part of my real-time DevOps learning journey.


👩‍💻 Maintained By

Suganya Subramanian
GitHub Profile
