## Creating a static website   

Note:
Step 1:
##### Create aws account : 
- Log in into your “aws” account with your credentials.   https://console.aws.amazon.com/s3  
- Authenticate and choose your region.  
![bucket-site](assets/Screenshot79.png)
https://eu-west-2.console.aws.amazon.com/s3/get-started?region=eu-west-2
 



Step 2: 
### Creating a bucket	In this section we see two separate accounts namespaces.
 
Global namespace allows your bucket name registered globally where no one can create the same name, meaning its unique across all aws account and region.
Bucket name also turns to be part of the endpoint URL.
Account regional namespace: buckets names are only registered or unique within specific region.
Step3 :
## Choose a bucket name,
 
  scroll down  click create


After navigate to Properties to enable static website hosting.
 

## Under Static website hosting click edit. 

	Enable (choose enable).
	As by default under S3 static website hosting shows disabled.
	 
	
	  Hosting type, Choose Host a static website.


Index Document.
Enter the file name of the index, index.html
 

 Click save changes.  

It is confirmed with the Bucket website endpoint at the bottom of the page.
http://quazi-africa.s3-website.eu-west-2.amazonaws.com

 
Copy the endpoint into a new browser and its results shows 403 Forbidden.
### Step 4 Click on Permissions 
By default Amazon S3 bucket blocks public access on aws accounts, editing public access to Enable grant permission to the public for read access.
Edit Block all public access, clear public access and click save.
### Step 5: Bucket Policy click on edit and paste a policy,
Now that S3 Public Access is been edited, We have bucket policy to grant public read access to the bucket.
The Policy here is an example for the bucket created on Amazon S3 which allows full access to the content.
Under the bucket, choose the bucket name  web-albert
Choose permission.
Under Bucket Policy, choose Edit.
In the space provided as the policy editor.
Paste you Bucket Policy.
scroll down and click save changes. 
Policy has successfully been added.
If  error shows invalid, check bucket name Or policy syntax if there are no errors. 
Also check Block Policy Access.
You can change the Resource to your prefered policy,Also try and change bucket name to your own S3 bucket name.
Choose save changes if changes is made to the policy on here.
This will be confirmed if changes are successfully been made.
### Step 6: Configure index.html
For static website hosting, enter the file name index document (index.html).
Open Virtual Studio Code
Create an index.html file 
Save the index.html file locally, the index document file name has to match the index document example index.hmtl(created) but not INDEX.HTML, as which ever you created has to be the same as this is case sensitive.
upload the index.html file into the console bucket list
Choose upload and click on add file.
Scroll down and click on upload to confirm the index.html file chosen.

### Step 7. Test the website with the end point.
navigate to your bucket name example. Web-albert.
Choose Properties and scroll down to static website hosting, choose bucket website endpoint.
http://web-albert.s3-website.eu-west-2.amazonaws.com
Copy and paste the endpoint into a browser / click on the endpoint, the index opens in a browser window.
The website showing is hosted on Amazon S3, website is available at the Amazon S3 website endpoint.
### Step 8 : Amazon CloudFront, a quick and safe content delivery network (CDN) service, Amazon CloudFront speeds up the distribution of websites, APIs, and video content to users all around the world.
Low Latency & High Speed: Reduces load times by distributing static and dynamic content globally via edge locations.
Create a CloudFront distribution.
Choose a free plan
Enter a distribution name, distribution type leave as Single website or app.
Click on NEXT.
Origin type:
Choose Amazon S3
S3 Origin domain, choose the website endpoint 
web-albert.s3-website.eu-west-2.amazonaws.com
Keep the Origin settings as default. Click Next
Under enable security we keep all values settings as default.
Click Next.
Next, Review and Create 
Scroll down to confirm create distribution.
This gives a distribution domain name and ID below
d26uu8y34qqkez.cloudfront.net
Distribution ID above gives .net 
### Step 9 : Updating record sets for domain and subdomain.
Having Cloudfront distribution created, alias record will be uodated in Route 53 to point to the new CloudFront distribution.


 
