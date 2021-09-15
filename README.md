# Test of GitHub Actions -> AWS Federation

As documented by Aidan Steele here — https://awsteele.com/blog/2021/09/15/aws-federation-comes-to-github-actions.html.

## How to deploy

Deploy the trust stack manually initially:

```
aws cloudformation deploy \
  --stack-name GitHubFederationTestTrustStack \
  --template-file trust.yaml \
  --capabilities CAPABILITY_NAMED_IAM
```

Set the `AWS_ROLE_ARN` GitHub secret.

Then run the GitHub action workflow (manually or via commit).

