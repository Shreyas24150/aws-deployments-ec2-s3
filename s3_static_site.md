
---

### 📄 `s3_static_site.md`

```markdown
# 🌐 Static Website Hosting with S3

## ✅ S3 Website URL:
`http://shreyas-cloudsite.s3-website-<region>.amazonaws.com`  
Example:  
`http://shreyas-cloudsite.s3-website-us-east-1.amazonaws.com`

---

## 🔧 Steps Followed:

### 1. Create an S3 Bucket
- Go to AWS S3 Console → Create Bucket
- Bucket Name: `shreyas-cloudsite`
- Region: Same as EC2 (e.g. us-east-1)
- Disable “Block all public access”
- Acknowledge warning and create bucket

---

### 2. Upload Files
- `index.html`
- `error.html`

---

### 3. Enable Static Website Hosting
- Go to Bucket → **Properties** → Static website hosting
- Enable it
  - Index document: `index.html`
  - Error document: `error.html`
- Save changes

---

### 4. Make Files Public

#### Add Bucket Policy:
Go to Bucket → **Permissions** → **Bucket Policy**, then paste:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::shreyas-cloudsite/*"
    }
  ]
}

