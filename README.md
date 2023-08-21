# URL-Shortener
URL Shortener using AWS services

This document explains the process of building a URL shortener tool using AWS cloudfront, AWS S3, AWS Lambda and AWS API Gateway. This tool is mainly helpful when we have to share long lengths of URLs (eg: signed URLs) to others. In case if we have to insert some pre-signed URL links in the cloudformation template, due to the template file size restrictions, we are limited to insert only certain number of URLs. With the help of this tool, we can increase that number to a greater extent. We can also use this tool to make the URL more readable.

Workflow:
**Webpage** *---requesting for shortened URL--->* **AWS cloudfront** *--->* **AWS API Gateway** *---forwards the request--->* **AWS Lambda** *---uploads an empty object in S3--->* **sends back the shortened URL as response** 
