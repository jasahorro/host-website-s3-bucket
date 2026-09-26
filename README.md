<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Host a Website on Amazon S3

**Project Link:** [View Project](https://nextwork.ai/projects/70e2d059-31ab-5f67-8c58-f5edbd451140?track=high)

**Author:** Maria Jasmin Ahorro

---

## Introducing Today's Project!

In this project, I'm going to host a static website on Amazon S3. I'll create an S3 bucket, upload the website files, turn on static website hosting, and make the files publicly accessible so anyone on the internet can visit my site.

### What is Amazon S3?

Amazon S3 (Simple Storage Service) is an object storage service that lets you store and retrieve any amount of data from anywhere. It's useful because it's highly durable, scales automatically, and can serve static websites (HTML, CSS, JavaScript and images) directly, with no web server to manage.

### Key tools and concepts

The key tools I used include Amazon S3, S3 buckets, the S3 static website hosting feature, and Access Control Lists (ACLs).

Key concepts I learnt include buckets and objects, AWS Regions, globally unique bucket names, Block Public Access settings, object ownership and ACLs, and bucket website endpoints.

### Challenges and wins

This project took me approximately 45 minutes to complete. The most challenging part was working out why my website showed a **403 Forbidden** error at first. The files were uploaded, but they weren't public yet. It was rewarding to fix the permissions and see the website load live from S3.

## How I Set Up an S3 Bucket

In this step, I'm going to create a new S3 bucket to store my website files.

Creating an S3 bucket took me only a few minutes. The Region I picked for my S3 bucket was the one closest to me, since a closer Region means lower latency.

S3 bucket names must be **globally unique**, because every bucket gets its own URL. No two AWS accounts anywhere can use the same bucket name.

## Upload Website Files to S3

In this step, I'm going to upload my website's files into the bucket.

I uploaded two things:

1. `index.html` - the main web page and the entry point of the website.
2. `NextWork - Everyone should be in a job they love_files` - the folder of images, CSS and JavaScript that `index.html` needs to display properly.

Both have to be uploaded because `index.html` holds the page's structure, while the assets folder holds everything that makes it look right. Without the folder, the page would load with broken images and no styling.

## Static Website Hosting on S3

In this step, I'm going to turn on static website hosting so my bucket can serve web pages.

Website hosting means making a website's files available on the internet so people can view them in a browser. To enable website hosting with my S3 bucket, I opened the bucket's **Properties** tab, enabled **Static website hosting**, and set `index.html` as the index document.

An Access Control List (ACL) is a set of rules that controls who can access specific buckets and objects. I enabled ACLs for this project so I could grant public read access to my website's files.

## Bucket Endpoints

In this step, I'm going to visit my website using the bucket's website endpoint.

Once static website hosting is enabled, S3 produces a **bucket website endpoint**, which is the public URL for the website.

When I first visited the bucket endpoint URL, I saw a **403 Forbidden** error. The reason for this error was that the objects in my bucket were still private by default, so visitors weren't allowed to read them.

## Success!

In this step, I'm going to make my website files public so the website loads for everyone.

To resolve the 403 error, I selected all the objects in my bucket and used **Actions > Make public using ACL**. That gave everyone read access to the files. After refreshing the endpoint URL, my website loaded successfully!

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/70e2d059-31ab-5f67-8c58-f5edbd451140?track=high)*
