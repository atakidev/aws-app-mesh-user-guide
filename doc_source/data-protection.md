# Data protection in AWS App Mesh<a name="data-protection"></a>

The AWS [shared responsibility model](http://aws.amazon.com/compliance/shared-responsibility-model/) applies to data protection in AWS App Mesh \(App Mesh\)\. As described in this model, AWS is responsible for protecting the global infrastructure that runs all of the AWS Cloud\. You are responsible for maintaining control over your content that is hosted on this infrastructure\. This content includes the security configuration and management tasks for the AWS services that you use\. For more information about data privacy, see the [Data Privacy FAQ](http://aws.amazon.com/compliance/data-privacy-faq)\.

For data protection purposes, we recommend that you protect AWS account credentials and set up individual user accounts with AWS Identity and Access Management \(IAM\)\. That way each user is given only the permissions necessary to fulfill their job duties\. We also recommend that you secure your data in the following ways:
+ Use multi\-factor authentication \(MFA\) with each account\.
+ Use SSL/TLS to communicate with AWS resources\.
+ Set up API and user activity logging with AWS CloudTrail\.
+ Use AWS encryption solutions, along with all default security controls within AWS services\.
+ Use advanced managed security services such as Amazon Macie, which assists in discovering and securing personal data that is stored in Amazon S3\.

We strongly recommend that you never put sensitive identifying information, such as your customers' account numbers, into free\-form fields such as a **Name** field\. This includes when you work with App Mesh or other AWS services using the console, API, AWS CLI, or AWS SDKs\. Any data that you enter into App Mesh or other services might get picked up for inclusion in diagnostic logs\. When you provide a URL to an external server, don't include credentials information in the URL to validate your request to that server\.

## Data encryption<a name="data-encryption"></a>

Your data is encrypted when using App Mesh\.

### Encryption at rest<a name="encryption-at-rest"></a>

All of the data and configurations that you create are encrypted at rest\.

### Encryption in transit<a name="encryption-in-transit"></a>

App Mesh endpoints use the HTTPS protocol\. All communication between the Envoy proxy and the App Mesh Envoy Management Service is encrypted\.  Communication between containers within virtual nodes is not encrypted, but this traffic doesn’t leave the network namespace\.