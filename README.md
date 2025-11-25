# aws_project2
📘 Instructions: Managing Cloud Object Storage with Amazon S3 (AWS Console)

Follow the steps below to create and manage an Amazon S3 bucket using the AWS Management Console.

🚀 1. Sign in to AWS Console

Visit the AWS Management Console

Log in with your AWS account credentials

In the top search bar, type S3

Click S3 (Simple Storage Service)

🪣 2. Create an S3 Bucket

Click Create bucket

Enter a unique bucket name

Choose your AWS Region

Under Object Ownership → select ACLs disabled (recommended)

Keep Block Public Access enabled (recommended unless hosting public files)

(Optional) Enable:

Bucket Versioning

Default Encryption

Click Create bucket

📤 3. Upload Files (Objects)

Open the bucket you created

Click Upload

Add files or folders

(Optional) Choose:

Storage Class (Standard / IA / Glacier)

Server-side Encryption

Click Upload

🔐 4. Manage Permissions
Bucket Permissions

Go to the Permissions tab

Configure:

ACLs (access control lists)

Bucket Policy (JSON rules)

CORS rules

Example public-read policy:
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}

🔄 5. Enable Versioning

In your bucket, open Properties

Scroll to Bucket Versioning

Click Enable

Save

Versioning protects against accidental deletes and keeps history.

🗂️ 6. Organize with Folders

Inside your bucket, click Create folder

Enter a name

Set encryption if required

Upload files into folders

📥 7. Download or Delete Objects
Download

Select an object → Click Download

Delete

Select the object → Delete

Confirm the deletion

If versioning is enabled, deleting only adds a delete marker — versions remain.

♻️ 8. Lifecycle Management

Use lifecycle rules to automate storage transitions.

Go to Management tab

Click Create lifecycle rule

Choose actions such as:

Move to IA after 30 days

Move to Glacier after 90 days

Auto-delete after X days

Save

🔒 9. Enable Default Encryption

Open Properties

Scroll to Default Encryption

Choose:

SSE-S3 (AES-256)

or SSE-KMS

Save

📊 10. Monitor the Bucket

Amazon S3 integrates with:

CloudWatch (usage metrics)

CloudTrail (access logs)

S3 Storage Lens (analytics dashboards)

Enable via Metrics and Monitoring sections.
