# [saltosti.com](http://www.saltosti.com)
A static site hosted on AWS S3

## Deployment

The `main` branch deploys the repository to S3 and invalidates CloudFront. Configure
these repository secrets:

- `AWS_ROLE_ARN`: IAM role trusted for GitHub Actions OIDC from this repository's
  `main` branch. Grant it only S3 sync permissions for the website bucket and
  `cloudfront:CreateInvalidation` for the site's distribution.
- `AWS_S3_BUCKET`: website bucket name.
- `DISTRIBUTION`: CloudFront distribution ID.

The bucket policy should provide public read access; the workflow does not set
object ACLs.
