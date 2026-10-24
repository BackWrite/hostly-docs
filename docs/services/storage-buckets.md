# S3-Compatible Object Storage Buckets

Store, retrieve, and serve user uploads, media files, and application backups with full S3 API compatibility.

---

## Features
- **100% S3 Compatibility**: Compatible with AWS SDKs, boto3, MinIO Client, and `@aws-sdk/client-s3`.
- **Zero Egress Bandwidth Fees**: No surprise fees when users download files from your storage bucket.
- **Presigned URLs**: Securely grant clients temporary read or write access without passing secrets through your backend.

---

## Configuration Example (`hostly.toml`)

```toml
[[storage]]
name = "user-avatars"
type = "bucket"
versioning = true
cors_allowed_origins = ["https://app.hostly.dev"]

[[services]]
name = "api"
type = "web"
[services.env]
S3_BUCKET_NAME = "${user-avatars.BUCKET_NAME}"
S3_ENDPOINT = "${user-avatars.ENDPOINT}"
S3_ACCESS_KEY_ID = "${user-avatars.ACCESS_KEY_ID}"
S3_SECRET_ACCESS_KEY = "${user-avatars.SECRET_ACCESS_KEY}"
```
