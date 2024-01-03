# Three-Tier-Web-Architecture

Referred through Amazon Three tier Web Architecture https://catalog.us-east-1.prod.workshops.aws/workshops/85cd2bb2-7f79-4e96-bdee-8078e469752a/en-US
For Application Code and other dependencies of this project refer to the above link.


Architecture will be Supposed to be as below:

![1](https://github.com/thatsyuviii/Three-Tier-Web-Architecture/assets/84862056/050d7bdf-8766-4da2-8307-623398cb0442)

In this architecture, a public-facing Application Load Balancer forwards client traffic to our web tier EC2 instances. The web tier is running Nginx webservers that are configured to serve a React.js website
and redirects our API calls to the application tier’s internal facing load balancer. The internal facing load balancer then forwards that traffic to the application tier, which is written in Node.js. 
The application tier manipulates data in an Aurora MySQL multi-AZ database and returns it to our web tier. Load balancing, health checks and autoscaling groups are created at each layer to maintain the availability of this architecture.

Steps Performed:

1. Created an S3 Bucket, For Storing Information

   ![2](https://github.com/thatsyuviii/Three-Tier-Web-Architecture/assets/84862056/e26cbdf0-0a12-410d-921c-99ded5b4f8a5)

2. Created an Iam Role for EC2 Instances

   ![3](https://github.com/thatsyuviii/Three-Tier-Web-Architecture/assets/84862056/cf86857e-3b83-47bb-bdeb-fa2cb89859b9)

3. Created VPC

   ![4 4 4 4](https://github.com/thatsyuviii/Three-Tier-Web-Architecture/assets/84862056/fd99a1e3-b6c5-4b27-9d27-e683e1b2f775)

4. Created Subnets

   ![5 5 5 5](https://github.com/thatsyuviii/Three-Tier-Web-Architecture/assets/84862056/6e1852d5-8d58-4745-bbb5-6d9a142de033)

5. Created Internet Gateway

   ![6](https://github.com/thatsyuviii/Three-Tier-Web-Architecture/assets/84862056/7a3a53b2-9d93-4126-ada0-a09264e78a39)

6. Created NAT Gateway

   ![7](https://github.com/thatsyuviii/Three-Tier-Web-Architecture/assets/84862056/8978dc1f-16d1-4b81-a23a-b97abb878b13)

7. Created Route Tables

   ![8](https://github.com/thatsyuviii/Three-Tier-Web-Architecture/assets/84862056/54e3c0c5-7bb9-414c-8d20-f8bd75cfaace)

8. Created Security Groups

   ![9](https://github.com/thatsyuviii/Three-Tier-Web-Architecture/assets/84862056/4fa26d3d-ffaf-4f56-aa65-38a7a679ac83)

9. Created Subnet Groups

   ![10](https://github.com/thatsyuviii/Three-Tier-Web-Architecture/assets/84862056/5d212c26-167f-4617-955c-3c6c564787ce)

10. Created Amazon Aurora Database with Read Replica

    ![11](https://github.com/thatsyuviii/Three-Tier-Web-Architecture/assets/84862056/afb5ee7f-b560-4915-b4b5-e3b150c650ba)

11. Created Demo EC2 instance for Configuring the instance, edited DBConfig.js adn added app-tier folder to S3

    ![12](https://github.com/thatsyuviii/Three-Tier-Web-Architecture/assets/84862056/0fdbcb78-af7f-444e-81ca-9ec2bf431222)

12. Configured Demo EC2 with MySQL installed

    ![13](https://github.com/thatsyuviii/Three-Tier-Web-Architecture/assets/84862056/7e9585ba-52a0-4805-86ad-4db2b4c0c089)

13. Created AMI from Demo EC2 instance for app tier 

    ![14](https://github.com/thatsyuviii/Three-Tier-Web-Architecture/assets/84862056/ccfffbed-1384-4e04-9989-26d1028d9386)

14. Created Target Groups for App Tier

    ![15](https://github.com/thatsyuviii/Three-Tier-Web-Architecture/assets/84862056/66b8fb9a-ff15-4dc4-ae9a-92ac86d4d461)

15. Created Application Load Balancer for App tier

    ![16](https://github.com/thatsyuviii/Three-Tier-Web-Architecture/assets/84862056/f999eb52-b62b-4b46-9623-deed786f4e58)

16. Created Launch Template from Demo EC2 AMI for App tier

    ![17](https://github.com/thatsyuviii/Three-Tier-Web-Architecture/assets/84862056/0d884024-776f-43ba-bb45-c90f0dd0e01a)

17. Created Auto Scaling Group from Launch Template of App tier

    ![18](https://github.com/thatsyuviii/Three-Tier-Web-Architecture/assets/84862056/1c0e08d4-f862-469d-be07-be5e159c6f4e)

18. Configured ngnix.conf file.

    ![19](https://github.com/thatsyuviii/Three-Tier-Web-Architecture/assets/84862056/f51b8df4-c9be-47be-90fb-34ad1990f2c2)

19. Added web-tier folder to S3

    ![20](https://github.com/thatsyuviii/Three-Tier-Web-Architecture/assets/84862056/d54bd66f-045b-44ec-8bae-7ca36b9618fe)

20. Created another DemoEC2 instance and configured it

    ![22](https://github.com/thatsyuviii/Three-Tier-Web-Architecture/assets/84862056/d13a9838-2e85-47e5-a772-077628c233a0)

21. Created AMI from Demo EC2 instance for web tier

    ![21](https://github.com/thatsyuviii/Three-Tier-Web-Architecture/assets/84862056/948fc8da-c6dd-47c8-a523-e3b31f3cee82)

22. Created Target Group for web tier

    ![24](https://github.com/thatsyuviii/Three-Tier-Web-Architecture/assets/84862056/0d698a89-78be-4ce8-934c-3f60a9116baf)

23. Created Load Balancer for web tier

    ![25](https://github.com/thatsyuviii/Three-Tier-Web-Architecture/assets/84862056/5476b51a-1f24-4c32-ba11-3082e17fea6f)

24. Created Launch Template from Demo EC2 AMI for web tier

    ![26](https://github.com/thatsyuviii/Three-Tier-Web-Architecture/assets/84862056/97955065-6078-4f65-8294-8113b0845740)

25. Created Auto Scaling Group for web tier

    ![27](https://github.com/thatsyuviii/Three-Tier-Web-Architecture/assets/84862056/ebb188f2-a720-4334-a925-5decc0e0e4ab)

Result:

![29](https://github.com/thatsyuviii/Three-Tier-Web-Architecture/assets/84862056/7be64396-4c4d-409a-9dab-149b0d7e3c47)

![28](https://github.com/thatsyuviii/Three-Tier-Web-Architecture/assets/84862056/5da6e28a-f535-4e57-b0d9-fafa6d5e76e4)















