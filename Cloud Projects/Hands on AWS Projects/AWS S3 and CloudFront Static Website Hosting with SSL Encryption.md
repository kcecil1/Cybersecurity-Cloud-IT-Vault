# AWS S3 and CloudFront Static Website Hosting with SSL Encryption

***

**Project Overview:** In this project, I developed a static website hosted on Amazon S3 and distributed it globally using Amazon CloudFront, Amazon’s content delivery network (CDN). I implemented SSL encryption to secure the website and its traffic using AWS Certificate Manager (ACM). Additionally, I applied advanced security configurations, such as setting up Origin Access Control (OAC), to restrict direct access to the S3 bucket, ensuring that the content could only be served through CloudFront.

**Skills Practiced:**

* **Amazon S3**
* **Amazon CloudFront**
* **AWS Certificate Manager (ACM)**
* **Bucket Policies and Access Management**

**Troubleshooting and Problem-Solving:** During the project, I encountered several challenges that required troubleshooting and deep technical investigation:

* **404 Errors from CloudFront**: After initially setting up CloudFront, I received 404 (Not Found) errors when trying to access the website. Through detailed investigation, I realized that I had uploaded my files inside a folder in the S3 bucket, which CloudFront couldn’t access because the file path didn’t match. I fixed this by ensuring the files (e.g., `index.html`) were in the correct path directly under the root of the bucket.
* **Incorrect Bucket Endpoint**: Initially, I mistakenly used the S3 website hosting endpoint instead of the S3 bucket endpoint, which resulted in incorrect content delivery. After seeing AWS’s recommendation to use the bucket endpoint for CloudFront, I made the necessary adjustments, which resolved the issue.
* **Origin Access Control (OAC) and Bucket Policy Conflicts**: Configuring OAC to restrict direct access to the S3 bucket required precise configuration of both CloudFront and the S3 bucket policy. Initially, I faced permission errors, but by correctly applying a bucket policy that allowed CloudFront to access the bucket through the OAC, I was able to resolve the problem.
* **SSL/HTTPS Configuration**: While setting up SSL encryption, I faced challenges with domain ownership validation. I opted for DNS validation through AWS Certificate Manager (ACM) and successfully completed the configuration, enabling HTTPS for secure communication.
* **Policy Updates**: At one point, the S3 bucket was allowing too much public access, which compromised security. To fix this, I updated the bucket policy to grant access only through CloudFront and ensured the correct permission was applied to restrict direct public access while still allowing CloudFront to fetch content.

**Project Goals:** The main objective was to learn and practice real-world cloud hosting and content delivery techniques using AWS services. The project also focused on security best practices, such as securing data in transit with SSL certificates, controlling access to cloud resources, and optimizing web content delivery globally.

**Key Takeaways:** Through troubleshooting, I learned the importance of precise configuration and understanding AWS services' interconnectedness. This experience not only reinforced my technical skills but also helped me develop better debugging strategies when working with cloud-based solutions.

**Challenges and Solutions:**

* **404 Errors**: Solved by restructuring the file path and ensuring correct object placement in the S3 bucket.
* **Incorrect Endpoint**: Fixed by switching to the correct S3 bucket endpoint.
* **Access Control Issues**: Resolved by configuring an appropriate bucket policy that allows CloudFront to access the S3 bucket via the OAC.
* **SSL Configuration**: Successfully handled SSL validation using DNS in AWS Certificate Manager.

**Outcome:** This project taught me valuable skills in web hosting using AWS, as well as critical troubleshooting techniques, which have broadened my ability to work with cloud technologies in a real-world environment.

***

<figure><img src="../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>



My issue here was that my three website files uploaded to the S3 bucket were in a folder instead of the root location inside of the bucket. After resolving that, then my webpage was viewable.

!\[\[Pasted image 20241009012842.png]] !\[\[Pasted image 20241009013004.png]] !\[\[Pasted image 20241009013103.png]] !\[\[Pasted image 20241009013141.png]] !\[\[Pasted image 20241009013217.png]] !\[\[Pasted image 20241009013306.png]] !\[\[Pasted image 20241009013334.png]] I pasted the permission policy from cloudfront to paste into the permissions of the S3 bucket to enable Origin Access Control and Origin Access Identity ( OAC, OAI)

[My Awesome S3 Website (d7rnsj5tvhvzo.cloudfront.net)](https://d7rnsj5tvhvzo.cloudfront.net/)
