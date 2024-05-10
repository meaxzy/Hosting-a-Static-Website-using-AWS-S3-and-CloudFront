# Hosting-a-Static-Website-using-AWS-S3-and-CloudFront

## Overview
Create a static website on Amazon S3 bucket(private bucket) but with public read policy assigned, using cloud front for Content Delivery Network.

### Requirements
1. An AWS account
2. The files to upload for your static website.

### STEPS TO FOLLOW

1. `Sign-in to your aws account and search for S3, click on s3 and create bucket as you can see in the images below, input your bucket name, note that your bucket name has to be unique, then leave every other settings as the default, scroll down and click on CREATE bucket`

![Screenshot-1](https://github.com/meaxzy/Hosting-a-Static-Website-using-AWS-S3-and-CloudFront/assets/85731275/25a4e030-1646-463d-a80c-bba24ac5b4fa)




2. `Upload objects into the created bucket, click on the bucket and open it, then click on upload, click on upload, it will give us option to upload files and upload folder, we would select upload folder since our objects resides in a folder after we must have uploaded everything successfully, we would now move to the next step`
`Move the content of the file inside of our folder to the bucket root directory, click on the folder, after it is open, select all the objects, then click on action and click on move, then it will open a page, then under the destination tab click on browse s3, it will open another page, just click on the name of your bucket, then click on choose destination, it will open another page, scroll down, then click on move, you have now successfully moved all the objects in to the bucket root directory`

![Screenshot-2](https://github.com/meaxzy/Hosting-a-Static-Website-using-AWS-S3-and-CloudFront/assets/85731275/4c84f174-8e16-4f1e-865b-ea461cadbed9)


3. `Next step is to create our cloudfront, so you will go to your search box and type cloudfront, click on it, click on create distribution`

![Screenshot-3](https://github.com/meaxzy/Hosting-a-Static-Website-using-AWS-S3-and-CloudFront/assets/85731275/92ad4c7c-774a-4b10-8c54-0da33f3d2d79)


4. `Now fill up the informations by clicking on the Origin domain name annd select your bucket name, then scroll down and under the origin access, select origin access control settings, then scroll down and click on create new OAC, leave evrything as default then on create. Then scroll down, look for default root object and input your landing page, for us our landing page is index.html, though it is optional, you can either leave it blank. But note that once you leave it blank, when you are trying to access the domain name that cloudfront would assign to you bucket, you will need to use "/index.html" to access your index page, so click on create`

![Screenshot-4](https://github.com/meaxzy/Hosting-a-Static-Website-using-AWS-S3-and-CloudFront/assets/85731275/f94207b0-4318-4ab1-8164-25958215e414)


5. `Next is to copy the bucket policy that was generated and go back to your s3 bucket, and under the permission tab, scroll down till you see bucket policy, edit it and paste the copied policy there , then save`

![Screenshot-5](https://github.com/meaxzy/Hosting-a-Static-Website-using-AWS-S3-and-CloudFront/assets/85731275/a2d3b443-8c3b-458f-994c-8440b41136a5)

![Screenshot-6](https://github.com/meaxzy/Hosting-a-Static-Website-using-AWS-S3-and-CloudFront/assets/85731275/b171a704-18b2-4f5f-81a5-dea8595ad793)

6. `The next step is to go back to our cloudfront, click on the distribution we created and you will see domain name that was assigned to our bucket, copy that domain name and paste in your browser to see if it is working, note that it might take some minutes before it start working for the first time`

![Screenshot-5](https://github.com/meaxzy/Hosting-a-Static-Website-using-AWS-S3-and-CloudFront/assets/85731275/5ba2aec1-d4ea-4b69-9bc3-3b96ba399942)


7. `We can now access my website through the distribution domain name assignes to my cloudfront distribution`

![Screenshot-7](https://github.com/meaxzy/Hosting-a-Static-Website-using-AWS-S3-and-CloudFront/assets/85731275/ff4b347d-f132-4697-b93a-5752f65a4b4d)
