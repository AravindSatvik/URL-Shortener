# URL-Shortener
URL Shortener using AWS services

This document explains the process of building a URL shortener tool using AWS cloudfront, AWS S3, AWS Lambda and AWS API Gateway. This tool is mainly helpful when we have to share long lengths of URLs (eg: signed URLs) to others. In case if we have to insert some pre-signed URL links in the cloudformation template, due to the template file size restrictions, we are limited to insert only certain number of URLs. With the help of this tool, we can increase that number to a greater extent. We can also use this tool to make the URL more readable.

## Workflow:
**Webpage** *---requesting for shortened URL--->* **AWS cloudfront** *--->* **AWS API Gateway** *---forwards the request--->* **AWS Lambda** *---uploads an empty object in S3--->* **sends back the shortened URL as response** 

## Procedure:
1. Create an S3 bucket. While creating the bucket, disable the **Block Public Access** option and enable ACLs. After the bucket is created, go to properties, click on **Edit Static Website Hosting**, enable and choose the hosting type as **Host a Static Website**. Specify the index document as index.html and save the changes.
2. Now, create a cloudfront distribution with the above created S3 bucket as origin. Here, we create cloudfront distribution to avoid CORS configuration and have a readable domain name.
3. Now, create an AWS lambda function with python as runtime and insert the url_shortener.py file uploaded in this repository.
