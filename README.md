# 🌐 Static Website Hosting using AWS S3 + CloudFront

This project demonstrates how to host a static website on the cloud using **AWS S3** and **CloudFront CDN**.
The website is publicly accessible over HTTPS and delivered through a global CDN.

---

## 📁 Project Files

```
index.html  
style.css  
script.js
```

These files form a simple static website.

---

## 🚀 Step-by-Step Deployment

### 1️⃣ Create S3 Bucket

1. Login to AWS Console
2. Open S3
3. Click **Create bucket**
4. Enter bucket name
5. Disable “Block public access”
6. Create bucket

---

### 2️⃣ Upload Website Files

Upload the following files to the bucket:

* index.html
* style.css
* script.js

Make sure they are in the root of the bucket.

---

### 3️⃣ Enable Static Website Hosting

1. Open bucket
2. Go to **Properties → Static website hosting**
3. Enable
4. Set index document:

```
index.html
```

Save changes.

---

### 4️⃣ Add Bucket Policy (Public Access)

Go to **Permissions → Bucket Policy** and paste:

```json
{
 "Version": "2012-10-17",
 "Statement": [
  {
   "Effect": "Allow",
   "Principal": "*",
   "Action": "s3:GetObject",
   "Resource": "arn:aws:s3:::YOUR-BUCKET-NAME/*"
  }
 ]
}
```

Replace `YOUR-BUCKET-NAME`.

---

### 5️⃣ Create CloudFront Distribution

1. Open CloudFront
2. Click **Create distribution**
3. Origin → Select S3 bucket
4. Viewer protocol policy → Redirect HTTP to HTTPS
5. Default root object:

```
index.html
```

6. Create distribution

Wait 5–10 minutes for deployment.

---

## 🌍 Website URL

CloudFront URL:

```
https://d29bdc5goo4kib.cloudfront.net
```

Open in browser to view the site.

---

## 🔐 Security Features

* HTTPS enabled
* CDN caching
* Public read policy
* CloudFront protection
* Faster global delivery

---
