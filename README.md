# Three-Tier-Web-Architecture

Referred through Amazon Three tier Web Architecture https://catalog.us-east-1.prod.workshops.aws/workshops/85cd2bb2-7f79-4e96-bdee-8078e469752a/en-US


Architecture will be Supposed to be as below:

![1](https://github.com/thatsyuviii/Three-Tier-Web-Architecture/assets/84862056/050d7bdf-8766-4da2-8307-623398cb0442)

In this architecture, a public-facing Application Load Balancer forwards client traffic to our web tier EC2 instances. The web tier is running Nginx webservers that are configured to serve a React.js website
and redirects our API calls to the application tier’s internal facing load balancer. The internal facing load balancer then forwards that traffic to the application tier, which is written in Node.js. 
The application tier manipulates data in an Aurora MySQL multi-AZ database and returns it to our web tier. Load balancing, health checks and autoscaling groups are created at each layer to maintain the availability of this architecture.

Steps Performed:

1. Created an S3 Bucket, For Storing Information
