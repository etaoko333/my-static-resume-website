# my-static-resume-website![s3 image](https://github.com/user-attachments/assets/f99f679b-4c6d-464c-8ea4-3fe75f62875f)


To create a CI/CD pipeline for hosting resume websites on Amazon S3 using GitHub and AWS CodePipeline, follow these steps:

Prerequisites
AWS Account: Ensure you have an AWS account.
GitHub Account: Have a GitHub account with a repository for your resume website.
AWS CLI: Install the AWS CLI and configure it with your IAM user.
Steps to Deploy the Application
Step 1: Create an S3 Bucket
Go to the AWS Management Console.
Navigate to S3 and click on Create Bucket.
Enter a unique bucket name (e.g., my-resume-website).
Choose a region and configure options as needed.
Disable "Block all public access" to allow public access to your website.
Click Create Bucket.

Step 2: Set Up Your GitHub Repository
Create a new repository on GitHub (e.g., resume-website).
Add your HTML, CSS, and JavaScript files for the resume website to the repository.
Commit and push your changes.

Step 3: Create an IAM Role for CodePipeline
Go to the IAM section in the AWS Management Console.
Click on Roles and then Create Role.
Select AWS Service and then choose CodePipeline.
Click on Next: Permissions.
Attach the following policies:
AmazonS3FullAccess
AWSCodeCommitFullAccess
AWSCodePipelineFullAccess
Click Next: Tags, then Next: Review.
Name your role (e.g., CodePipelineRole) and create it.

Step 4: Create a CodePipeline
Go to the AWS Management Console and navigate to CodePipeline.
Click Create Pipeline.
Enter a pipeline name (e.g., ResumeWebsitePipeline).
Choose the service role you created earlier (e.g., CodePipelineRole).
Click Next.
For Source Provider, select GitHub:
Connect your GitHub account.
Select the repository and branch (e.g., main).
Click Next.
For Build Provider, select AWS CodeBuild:
Click Create a build project.
Enter a project name (e.g., ResumeWebsiteBuild).
Click Continue to CodePipeline.
For Deploy Provider, select Amazon S3:
Choose the S3 bucket you created earlier.
Set the Extract file before deploy option if you have a zip file.
Click Next and review your settings.
Click Create Pipeline.

Step 5: Test the Pipeline
Push a new commit to your GitHub repository.
Go to the CodePipeline console and monitor the pipeline execution.
If successful, your resume website should be hosted on S3.

Step 6: Configure S3 Static Website Hosting
Go to your S3 bucket.
Click on Properties.
Under Static website hosting, enable it.
Set the Index document (e.g., index.html) and Error document (e.g., error.html).
Save changes.

Step 7: Access Your Resume Website
After deployment, access your website using the S3 endpoint URL provided in the static website hosting settings.

Final Notes
Ensure your bucket policy allows public access to the files.
You can automate the process further by integrating with CloudFront for CDN capabilities.
This setup will allow you to automatically deploy your resume website to S3 whenever you push changes to the GitHub repository.



<img width="960" alt="2025-01-02 (3)" src="https://github.com/user-attachments/assets/2be6035a-bc00-414d-8b6e-9beec35c0cc7" />


<img width="960" alt="2025-01-02 (4)" src="https://github.com/user-attachments/assets/3738a220-1ad3-4065-8de5-b78da5dbb34f" />



<img width="960" alt="2025-01-02 (2)" src="https://github.com/user-attachments/assets/ecd07c85-7c3e-434a-b27f-b1e009e3db10" />

<img width="960" alt="2025-01-02 (5)" src="https://github.com/user-attachments/assets/c55c188c-e4df-42dc-a090-7afc8cd45e0b" />


<img width="960" alt="2025-01-02 (7)" src="https://github.com/user-attachments/assets/185aecfd-81d1-49e3-85ef-414d3ca7e567" />

