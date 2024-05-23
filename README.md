PROJECT: HOSTING A STATIC WEBSITE USING AMAZON S3
Objective:
To host a static website using Amazon S3 by creating a bucket, uploading files, enabling static website hosting, configuring access permissions, and successfully deploying the website.

Step-by-Step Guide
1. Created an S3 Bucket and Allowed Public Access
Step Overview:
Creating an S3 bucket is the first step where all your website files will be stored. Public access is enabled to ensure that anyone on the internet can view your website.

Detailed Steps:

- Navigate to Amazon S3 Console: Open the AWS Management Console, and navigate to the S3 service.
  
- Create a New Bucket:
  Click on "Create bucket".
  Enter a unique bucket name (e.g., my-static-website).
  Select the appropriate AWS region for your bucket.
  Leave the default settings for other options and click "Create bucket".
  Configure Public Access:
  Select the newly created bucket.
  
- Go to the "Permissions" tab.
  Click on "Block public access" and disable the "Block all public access" option. Confirm the changes.
  This step is crucial to allow public access to the contents of your bucket.


2. Uploaded My Files to the Bucket
Step Overview:
Upload your website’s files (HTML, CSS, JavaScript, images, etc.) to the S3 bucket.

Detailed Steps:

- Navigate to the Bucket:
- Open the S3 console, and select your bucket (my-static-website).
- Upload Files:
- Click the "Upload" button.
- Drag and drop your website files (e.g., index.html, styles.css, script.js) or use the file selector.
- Click "Upload" to transfer the files to your S3 bucket.


3. Enabled Static Website Hosting Feature of the Bucket Under Bucket Properties
Step Overview:
Enable the S3 bucket to serve your files as a static website.

Detailed Steps:

Static Website Hosting Configuration:

- Select your bucket and go to the "Properties" tab.
- Scroll down to the "Static website hosting" section.
- Choose "Use this bucket to host a website".
- Enter the name of your index document (e.g., index.html) and an error document (e.g., error.html).
  Save the changes.
- Retrieve Website URL:
- Note the endpoint URL provided by AWS (e.g., http://my-static-website.s3-website-us-west-2.amazonaws.com).


4. Opened the Website URL Under the Static Hosting and Encountered a 403 Forbidden Error
Step Overview:
Attempt to access your website using the provided URL, and troubleshooting the 403 Forbidden error encountered.

Detailed Steps:

Access the Website:
- Open a web browser and navigate to the URL provided by S3.
- Encounter a 403 Forbidden error, indicating an issue with access permissions.


5. Added a Bucket Policy Through Policy Generator
Step Overview:
Create and apply a bucket policy to grant public read access to all objects within the bucket.

Detailed Steps:

- Navigate to Bucket Policies:
- Go to the "Permissions" tab of your bucket.
- Click "Bucket Policy".
- Generate Policy Using AWS Policy Generator:
- Open the AWS Policy Generator.
  Select "S3 Bucket Policy" as the Policy Type.
  Add a Statement:
  Effect: Allow
  Principal: *
  Action: s3:GetObject
  ARN: arn:aws:s3:::my-static-website/*
- Generate the policy and copy the JSON output.
- Apply the Policy:
- Paste the JSON policy into the Bucket Policy editor and save the changes.

6. Refresh your webpage 
