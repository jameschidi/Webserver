# Webserver
Prerequisites
	1. Create a role on IAM which allow access to sync from ec2 to S3
	2. Create an EFS system
	3. Create an s3 bucket named Webserver
	4. Create two networks with proper routes. Both with internet access (us-east-1 and us-west-1) 

Deployment Steps
	•  The static content of the webserver will be hosted on us-east-1.
	• The first SSR will be hosted us-east-1 and the other on us-west-1.
	• Create a filesystem and mount on both EC2 using a common folder between the two hosts.
	• Clone the project from the GitHub repository on the Filesystem on the EC2 on us-west-1.
	• Build the project using the instruction on the repository readme file.
	• Verify the build is available of the filesystem path of the other ec2 on us-east-1.
	• Sync the build to S3 as the static source with using IAM keys (use roles).
	• Deploy the SSR project on both ec2.
	• Create a application load balancer for each ec2 instance.
	• Verify the deployment on both S3 and the 2 hosts. Verify the on S3 by checking the url on your browser. Verify the deployment on both ec2 by checking the Load Balancer on your browser.
	• Consolidate all the 3 origins on CloudFront. 
	• Check the CloudFront domain on your browser.
