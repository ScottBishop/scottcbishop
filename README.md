# Simple developer website for [scottcbishop.com](https://scottcbishop.com)

## Deployed with AWS S3, Cloudfront, Route 53, and Certificate Manager.

### To deploy:

1. Install aws command line client (if not already installed)

`$ pip install awscli`

2. Sync project folder with s3 bucket (run from root website directory) and 

```
$ aws s3 sync --acl public-read --sse --delete . s3://scottcbishop.com
```

3. Invalidate cloudfront cache so changes are reflected correctly.

```
$ aws cloudfront create-invalidation --distribution-id I2FQMQC4UT31T5 --paths '/*'
```
