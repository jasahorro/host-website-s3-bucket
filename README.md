<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Host a Website on Amazon S3

**Project Link:** [View Project](https://nextwork.ai/projects/70e2d059-31ab-5f67-8c58-f5edbd451140)

**Author:** Maria Jasmin Ahorro  
**Email:** jasminahorro23@gmail.com

---

![Image](https://nextwork.ai/overjoyed_magenta_proud_yak/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_5d4474f9)

## Introducing Today's Project!

### Project overview

In this project, I will demonstrate how to set up an Amazon S3 bucket, upload website files, and configure static website hosting. I'm doing this project to learn how cloud storage works and how to make a website publicly accessible on AWS.

### Tools and concepts

Services I used were Amazon S3 (Simple Storage Service) within the AWS Management Console.

Key concepts I learnt include:

Globally Unique Bucket Names: S3 bucket names are unique across all AWS accounts and regions worldwide.

Static Website Hosting vs. Object Permissions: Enabling static website hosting generates a public bucket endpoint URL, but the underlying uploaded files remain private by default.

Access Control Lists (ACLs): Rules that grant object-level access control, allowing individual files like index.html and media assets to be made publicly readable to resolve 403 Forbidden errors.

Bucket Policies: Centralized JSON-based security policy rules that manage bucket-wide permissions and enforce explicit protections (such as denying s3:DeleteObject actions).

Resource Cleanup: Deleting S3 objects and buckets after project completion to prevent unwanted cloud charges.

### Time, challenges, and wins

This project took me approximately 45 minutes to complete from start to finish. The most challenging part was understanding why my bucket endpoint URL initially returned a 403 Forbidden error and configuring object permissions using ACLs and JSON bucket policies to fix it. It was most rewarding to see my website successfully go live on the internet and then test a custom bucket policy to protect my files from accidental deletion.

## How I Set Up an S3 Bucket

### What I did in this step

In this step, I will create a globally unique S3 bucket in Amazon S3 with ACLs enabled and public access unblocked because I need a dedicated cloud storage container to store and publicly serve my static website files.

### How long it took to create the bucket

Creating an S3 bucket took me less than a minute to configure and set up in the AWS Management Console.

### Region selection

The Region I picked for my S3 bucket was Asia Pacific (Singapore) ap-southeast-1 because it is geographically close to my location in the Philippines, reducing latency for website access and providing full availability for all Amazon S3 features.

### Understanding bucket name uniqueness

S3 bucket names are globally unique! This means no two AWS accounts anywhere in the world can share the exact same bucket name. Once a name is taken by any user across any AWS region, it cannot be used by anyone else until that bucket is deleted.

![Image](https://nextwork.ai/overjoyed_magenta_proud_yak/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_ba6d42ad)

## Upload Website Files to S3

### What I did in this step

In this step, I will upload my index.html file and the unzipped folder of website image assets directly into my Amazon S3 bucket because an S3 bucket needs the underlying code and static media files before it can serve and render a website.

### Files I uploaded

I uploaded two files to my S3 bucket - they were the index.html file, which contains the structural code and design for the website, and an unzipped folder containing all the website's image assets.

### How the files work together

Both files are necessary for this project as the index.html file provides the structural framework and code for the website, while the unzipped folder contains all the image assets that index.html references to correctly render and display the visuals on the web page.

![Image](https://nextwork.ai/overjoyed_magenta_proud_yak/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_a265af88)

## Static Website Hosting on S3

### What I did in this step

In this step, I will enable static website hosting in my S3 bucket settings and specify index.html as the index document because an S3 bucket acts only as a general storage container by default, and enabling hosting instructs AWS to generate a unique website endpoint URL that serves my HTML and media files as a functional web page to visitors over the internet.

### Understanding website hosting

Website hosting means storing your website's files—such as HTML documents, images, and stylesheets—on a web server so they can be accessed by visitors over the internet. Even if you write a perfect HTML file on your local computer, no one else can view it until those files are uploaded to a publicly reachable storage location or web server.

In this project, we configure an Amazon S3 bucket to serve as our host by uploading our index.html file and image assets, turning on static website hosting, unblocking public access, and enabling Access Control Lists (ACLs) to grant public read permissions so visitors worldwide can load the site via the generated bucket website endpoint URL.

### How I enabled website hosting

To enable website To enable website hosting with my S3 bucket, I navigated to the Properties tab of my bucket, scrolled down to the Static website hosting section, and selected Edit. I then selected Enable under Static website hosting, chose Host a static website as the hosting type, entered index.html as the Index document, and saved my changes to generate the Bucket website endpoint.with my S3 bucket, I...

### Access Control Lists (ACLs)

An ACL is a set of rules in Amazon S3 that defines which AWS accounts or groups are granted access and what permissions they have for a bucket or individual objects. In this project, I enabled ACLs and selected the "Bucket owner preferred" setting so I could manage permissions for each website file individually, allowing me to grant public read access to index.html and the image assets so my static website can be viewed on the internet.

![Image](https://nextwork.ai/overjoyed_magenta_proud_yak/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_c22c54c0)

## Bucket Endpoints

### Understanding bucket endpoint URLs

Once static website is enabled, S3 produces a bucket endpoint URL, which is a unique web address generated by Amazon S3 that allows anyone on the internet to access and view your hosted website files as a functional web page in their browser.

### What I saw when I tested the endpoint

When I first visited the bucket endpoint URL, I saw a 403 Forbidden access denied error page instead of my hosted website.

The reason for this error was that objects uploaded to Amazon S3—such as my index.html file and the folder containing my image assets—are set to private by default to ensure security and prevent unauthorized access. Even though I enabled static website hosting on the bucket to generate a public URL, the underlying files themselves were still blocked from public view. To fix this and allow visitors on the internet to load and render the web page, I needed to explicitly configure public read permissions for these files using Access Control Lists (ACLs).

![Image](https://nextwork.ai/overjoyed_magenta_proud_yak/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_22ce4daf)

## Success!

### What I did in this step

In this step, I will make the uploaded website files in my S3 bucket publicly accessible using Access Control Lists (ACLs) because AWS keeps objects private by default, and granting public read permissions is necessary to resolve the 403 Forbidden error and allow visitors to view the website.

### How I resolved the 403 error

To resolve this 403 Forbidden error, I selected both the index.html file and the folder of image assets in my S3 bucket's Objects tab, chose Actions, and selected Make public using ACL. I then confirmed the action by clicking Make public, which granted public read permissions to the files and allowed the website to render properly when loading the bucket endpoint URL.

![Image](https://nextwork.ai/overjoyed_magenta_proud_yak/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_5d4474f9)

## Bucket Policies

### What I did in this extension

In this project extension I'm about to attach a custom JSON bucket policy to my S3 bucket that explicitly denies s3:DeleteObject permissions for index.html. I'm doing this so that I can learn how bucket policies provide fine-grained resource security and test how to protect critical website files from accidental or unauthorized deletion.

### Understanding bucket policies

An alternative to ACLs are bucket policies, which are JSON-based access control rules attached directly to an S3 bucket that define permissions for resources across the entire bucket. The benefit of using bucket policies is that they offer centralized, highly detailed security controls—allowing you to manage complex rules like denying file deletions, requiring specific conditions, or making all objects public at once—while ACLs are useful for managing access rights on an individual, object-by-object level.

![Image](https://nextwork.ai/overjoyed_magenta_proud_yak/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_sm2sm2sm)

### What my bucket policy does

My bucket policy explicitly denies s3:DeleteObject permissions for the index.html file in my bucket to everyone ("Principal": "*"). I tested this by attempting to select index.html in the Objects tab and clicking Delete, and saw a 403 Access Denied error listing index.html under the Failed to delete panel, proving that the policy successfully prevented the file from being removed.

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/70e2d059-31ab-5f67-8c58-f5edbd451140)*
