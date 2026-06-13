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
 
1.Global namespace allows your bucket name registered globally where no one can create the same name, meaning its unique across all aws account and region.

2.Bucket name also turns to be part of the endpoint URL.

3.Account regional namespace: buckets names are only registered or unique within specific region.

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
1.By default Amazon S3 bucket blocks public access on aws accounts, editing public access to Enable grant permission to the public for read access.

2.Edit Block all public access, clear public access and click save.

### Step 5: Bucket Policy click on edit and paste a policy.

1.Now that S3 Public Access is been edited, We have bucket policy to grant public read access to the bucket.

2.The Policy here is an example for the bucket created on Amazon S3 which allows full access to the content.

3.Under the bucket, choose the bucket name  web-albert

4.Choose permission.

5.Under Bucket Policy, choose Edit.

6.In the space provided as the policy editor.

7.Paste you Bucket Policy.

8.Scroll down and click save changes. 

9.Policy has successfully been added.

10.If  error shows invalid, check bucket name Or policy syntax if there are no errors. 

11.Also check Block Policy Access.

12.You can change the Resource to your prefered policy,Also try and change bucket name to your own S3 bucket name.

13.Choose save changes if changes is made to the policy on here.

14.This will be confirmed if changes are successfully been made.

### Step 6: Configure index.html
1.For static website hosting, enter the file name index document (index.html).

2.Open Virtual Studio Code.

3.Create an index.html file.

4.Save the index.html file locally, the index document file name has to match the index document example index.hmtl(created) but not INDEX.HTML, as which ever you created has to be the same as this is case sensitive.

5.Upload the index.html file into the console bucket list.

6. Choose upload and click on add file.

7.Scroll down and click on upload to confirm the index.html file chosen.

### Step 7. Test the website with the end point.
1.Navigate to your bucket name example. Web-albert.

2.Choose Properties and scroll down to static website hosting, choose bucket website endpoint.

http://web-albert.s3-website.eu-west-2.amazonaws.com

3.Copy and paste the endpoint into a browser / click on the endpoint, the index opens in a browser window.

4.The website showing is hosted on Amazon S3, website is available at the Amazon S3 website endpoint.

### Step 8 : Amazon CloudFront, a quick and safe content delivery network (CDN) service, Amazon CloudFront speeds up the distribution of websites, APIs, and video content to users all around the world.

5.Low Latency & High Speed: Reduces load times by distributing static and dynamic content globally via edge locations.

6.Create a CloudFront distribution.

7.Choose a free plan.

8.Enter a distribution name, distribution type leave as Single website or app.

9.Click on NEXT.

10. Origin type:
11. 
11.Choose Amazon S3.

12.S3 Origin domain, choose the website endpoint.

web-albert.s3-website.eu-west-2.amazonaws.com.

13.Keep the Origin settings as default. Click Next.

14.Under enable security we keep all values settings as default.

15.Click Next.

16.Review and Create,Scroll down to confirm create distribution.

17.This gives a distribution domain name and ID below
d26uu8y34qqkez.cloudfront.net

Distribution ID above gives .net 

### Step 9 : Updating record sets for domain and subdomain.
Having Cloudfront distribution created, alias record will be uodated in Route 53 to point to the new CloudFront distribution.


 
