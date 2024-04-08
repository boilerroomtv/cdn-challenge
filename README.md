# Boiler Room CDN Challenge

Create a solution using AWS S3 and CloudFront to serve static assets (images and videos), with a focus on performance optimization through differentiated caching strategies based on file types.

## Setup

1. Create an AWS account on Free Tier.
	1. Setup a new AWS S3 bucket configured for static website hosting:
	2. Set the bucket policy to allow public read-only access for all objects.
	3. Upload the [/assets](example assets in this repo) to your bucket.
2. Create a CloudFront distribution with your S3 bucket as the origin:
	1. Create behaviours to cache files according to their type using the path pattern feature:
		1. JPG & PNG: 12 hours
		2. GIF: 24 hours
		3. MP4: 48 hours
	2. Setup 2 response policies that adds headers that instruct the browser how to cache files locally:
		1. JPG & PNG: 24 hours
		2. GIF & MP4: 72 hours
	3. Configure the distribution to support HTTPS

## Delivery
Document your setup in a Google Doc:

- Include the login details to the AWS account
- Include demo links for each file type
- Include screenshots
