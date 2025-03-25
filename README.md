## AWS-Project-Game-S3-GitHub

This repo contains the code files used in this [YouTube video](https://youtu.be/biYVW1TMYAU).

This is the [AWS Game](http://mygameinaws-memeproject.s3-website-us-east-1.amazonaws.com/), enjoy it!.

# Creating a AWS S3 Bucket
To host the webpage we have to create a S3 bucket in AWS, so find the S3 option and click in create a Bucket.

![image](https://github.com/user-attachments/assets/8d1275ed-d6dc-4427-b581-fff855d2bd7c)

We are going to us e a General Puspose bucket.
To choose a name, this has to be unique across all the AWS.

![image](https://github.com/user-attachments/assets/69b59ded-d1b3-46b9-8eff-2dc3c7f4cb28)

Allow Public Acces for this bucket. This option is not recommended if you are working with buckets, but for this projects is fine.

![image](https://github.com/user-attachments/assets/b8f207a6-f31b-4d97-9c07-6a3af35ba6b0)

Once your new bucket is done, go to properties and enable the Static Website Hosting, and add the index file name, that usually is the same name.

![image](https://github.com/user-attachments/assets/e122fcab-5114-46a0-b2be-98dc5b0108de)

Then we have to allow public acces to the files like pictures. For this we have to add a Bucket policy.

![image](https://github.com/user-attachments/assets/47cb02d6-55d4-4b9d-9aef-2427a2cbe51c)

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject", 
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::THE-NAME-OF-YOUR-BUCKET/*"
        }
    ]
}

```

