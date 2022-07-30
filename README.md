# cfn-static-website-starter-challenge
Deploying an S3 bucket and EC2 instance with Apache2 server on top that's able to access that bucket object to deploy a static website


``
 aws cloudformation create-stack --stack-name [your-preferred-name] --region [your-region] --template-body file://cfn-challenge.yml --parameters file://parameters.json --capabilities CAPABILITY_NAMED_IAM [--profile udacity2]     
 ```
Upload your static .html to the created bucket via AWS Management Console.
SSH to your EC2 instance and run the following commands to copy the data to your apache server index.
```
cd /var/www/html
sudo aws s3 cp s3://[your-bucket-name]/index.html index.html
```
Lastly, access your public ipv4/DNS of your EC2 instance in http, append /index.html and you're in.
