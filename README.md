# [saltosti.com](http://www.saltosti.com)
A static site hosted on AWS S3

## Deployment

The `main` branch deploys the repository to S3 and invalidates CloudFront. Configure
these existing repository secrets:

- `AWS_S3_BUCKET`: website bucket name.
- `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY`: credentials for S3 upload.
- `DISTRIBUTION`: CloudFront distribution ID.
- `AWS_ACCESS_KEY_ID_CLOUDFRONT` and `AWS_SECRET_ACCESS_KEY_CLOUDFRONT`: credentials
  for CloudFront invalidation.

This workflow reuses the existing AWS credentials and resources; it does not
require an OIDC role or other AWS setup. S3 object uploads retain the existing
`public-read` ACL behavior.
