Ever dreamt of crafting a website and **turbocharging its speed through CloudFront magic?** Here, we blend **S3 simplicity with CloudFront prowess.** Breaking free from the static norm and embracing the dynamic world of caching wonders!!!

The steps to getting it done are highlighted below. 

**Table of Contents**

- [Bucket Creation](#bucket-creation)
- [Enabling Static Website Hosting](#enabling-static-website-hosting) 
- [Configure Bucket Policy To Allow Public Access](#configure-bucket-policy-to-allow-public-access)
- [File Upload to Bucket](#file-upload-to-bucket)
- [Creating Cloudfront Distribution](#creating-cloudfront-distribution)
- [Updating S3 Policy for Cloudfront](#updating-s3-policy-for-cloudfront)
- [Time To Live](#time-to-live)
- [Cache Invalidation](#cache-invalidation)
- [Cleanup](#cleanup)

### Bucket Creation
1. Login into your AWS account
2. On your AWS Management Console, search for S3.
3. Click on Create a Bucket
   
![Creating Bucket](https://github.com/Elizzy01/Deploying-a-Static-Website-using-AWS-S3-and-Cloudfront/assets/98459984/07580a28-114c-494d-a8bb-85babe51948c)

4. Create a bucket with the following configuration
 - Name: has to be globally unique
 - AWS Region: us-east-1
 - Disable ACL
5. Uncheck the Block all public access box
 - `Check the box that acknowledges that you understand the
current settings might result in this bucket and all the objects
within becoming public.`

![Bucket Public](https://github.com/Elizzy01/Deploying-a-Static-Website-using-AWS-S3-and-Cloudfront/assets/98459984/daccee35-1b25-41f1-9e1c-3f734425b37c)

- Leave everything else as their default configuration.
- Click on Create Bucket.

![Uploading bucket](https://github.com/Elizzy01/Deploying-a-Static-Website-using-AWS-S3-and-Cloudfront/assets/98459984/30bd845a-1567-40e0-9916-80d563cfd18b)

### Enabling Static Website Hosting
**Click on the newly-created bucket, and go to the Properties tab**
6. Scroll down to the end to Static Website Hosting
7. Click on the edit button
8. Check the Enable radio button. After this, a list of 
the static website hosting configurations will appear. Follow the instructions below:
 - Hosting Type: Host a static website
 - Index document: type index.html
 - Click on Save Changes

### Configure Bucket Policy To Allow Public Access

9. Go to the Permissions tab of your bucket.
10. Scroll down to Bucket Policy, and click on edit.

![Edit permissions for cloudfront](https://github.com/Elizzy01/Deploying-a-Static-Website-using-AWS-S3-and-Cloudfront/assets/98459984/2dea7443-2be4-4e0c-bbad-dbb56db3e5aa)

12. There are 2 ways to add a bucket policy:

 - Checking Policy examples and copying the ones for your
use case.
 - Using a Policy generator.
- We’ll be using the second method for this project.
  
12. Click on Policy Generator.
![Edit permissions for cloudfront](https://github.com/Elizzy01/Deploying-a-Static-Website-using-AWS-S3-and-Cloudfront/assets/98459984/2dea7443-2be4-4e0c-bbad-dbb56db3e5aa)

13. You will be redirected to the AWS Policy Generator Page. Fill out the
fields using the following configuration:
```
Policy Type: **S3 Bucket Policy**
Effect: Allow
Principal: *
AWS Service: Amazon S3
Actions: Check the GetObjects checkbox
ARN: Paste the ARN for your S3 bucket here, and then add '/*'.
Here’s an example of how it should look like:
arn:aws:s3:::<bucket-name>/*

```
**Replace <bucket-name> with the name of your bucket.**

13. Click on Add Statement > Generate Policy.
