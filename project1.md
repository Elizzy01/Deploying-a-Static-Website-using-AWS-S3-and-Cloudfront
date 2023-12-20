Ever dreamt of crafting a website and **turbocharging its speed through CloudFront magic?** Here, we blend **S3 simplicity with CloudFront prowess.** Breaking free from the static norm and embracing the dynamic world of caching wonders!!!

The steps to geting it done are highlighted below. 

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

![Uploading bucket](https://github.com/Elizzy01/Deploying-a-Static-Website-using-AWS-S3-and-Cloudfront/assets/98459984/30bd845a-1567-40e0-9916-80d563cfd18b)
