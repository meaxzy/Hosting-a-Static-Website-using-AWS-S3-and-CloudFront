# Hosting-a-Static-Website-using-AWS-S3-and-CloudFront

## Overview
Create a static website on Amazon S3 bucket(private bucket) but with public read policy assigned, using cloud front for Content Delivery Network.

### Requirements
1. An AWS account
2. The files to upload for your static website.

### STEPS TO FOLLOW

1. `Sign-in to your aws account and search for S3, click on s3 and create bucket as you can see in the images below, input your bucket name, note that your bucket name has to be unique, then leave every other settings as the default, scroll down and click on CREATE bucket`
![s3 search]("C:\Users\HP\Pictures\Screenshots\Screenshot-1.png")
![fill s3](<images/create s3.PNG>)



2. `Upload objects into the created bucket, click on the bucket and open it, then click on upload, click on upload, it will give us option to upload files and upload folder, we would select upload folder since our objects resides in a folder after we must have uploaded everything successfully, we would now move to the next step`
![alt text](<images/upload folder.PNG>)



3. `Move the content of the file inside of our folder to the bucket root directory, click on the folder, after it is open, select all the objects, then click on action and click on move, then it will open a page, then under the destination tab click on browse s3, it will open another page, just click on the name of your bucket, then click on choose destination, it will open another page, scroll down, then click on move, you have now successfully moved all the objects in to the bucket root directory`
![alt text](<images/move files to bucket root.PNG>)


4. `Next step is to create our cloudfront, so you will go to your search box and type cloudfront, click on it, click on create distribution`
![alt text](<images/search cloudfront.PNG>)
![alt text](<images/create distribution.PNG>)



5. `Now fill up the informations by clicking on the Origin domain name annd select your bucket name, then scroll down and under the origin access, select origin access control settings, then scroll down and click on create new OAC, leave evrything as default then on create. Then scroll down, look for default root object and input your landing page, for us our landing page is index.html, though it is optional, you can either leave it blank. But note that once you leave it blank, when you are trying to access the domain name that cloudfront would assign to you bucket, you will need to use "/index.html" to access your index page, so click on create`

![alt text](<images/cloundfront process.PNG>)
![alt text](<images/cloudfront OAC.PNG>)
![alt text](<images/cloudfront document.PNG>)


6. `Next is to copy the bucket policy that was generated and go back to your s3 bucket, and under the permission tab, scroll down till you see bucket policy, edit it and paste the copied policy there , then save`
![alt text](<images/copy policy.PNG>)
![alt text](<images/paste bucket policy.PNG>)


7. `The next step is to go back to our cloudfront, click on the distribution we created and you will see domain name that was assigned to our bucket, copy that domain name and paste in your browser to see if it is working, note that it might take some minutes before it start working for the first time`
![click domain](<images/click domain.PNG>)


8. `We can now see that our domain name has now successfully rendered our landing page`
![final](images/final.PNG)


So, this is how to host a static webpage on a private bucket and still be able to access it using CloudFront.
