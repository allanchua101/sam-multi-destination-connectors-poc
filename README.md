# AWS SAM Multi-Destination Connectors POC

AWS SAM Connectors are SAM-based abstract resource types used for provisioning IAM permissions for serverless application resources. They provide value by reducing the level of expertise required in authoring IAM permissions.

### Why Use Multi-Destination Connectors?

This feature has been released to address the challenges associated with the first version of the SAM connectors. It helps by:

- Grouping together multiple connection definitions under the resource construct.
- Removes the need to remember various property names associated with policy template property usage. (EG. TableName, QueueName, BucketName)
- Offers lower code lines required to establish multiple connections to a function.

### SAM CLI Improvement Opportunities

- Support the following resources:
  - Secrets manager
  - SSM parameter
  - SES
  - Rekognition
  - KMS
  - CloudWatch
  - CodeCommit
  - CodePipeline
  - CodeBuild
  - CodeDeploy
  - Firehose
- Reference to templated values would be cool but `ARN` targeting is much more interesting.
- Syntax of multi-destination connector could still get improved.

```yaml
WriteConnectors:
  - Id: SampleTableA
  - Id: SampleTableB
  - Arn: arn:aws:secretsmanager:ap-southeast-1::secret:sample-credential-Lw92LOwe
```

### What do you need

- NodeJS 18+
- SAM CLI (Latest Version)
- AWS named Profile
- AWS CLI

### References

- [AWS SAM Connector Guide](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/managing-permissions-connectors.html)
- [An opinionated view of SAM Connectors](https://medium.com/@ac052790/an-opinionated-view-of-aws-sam-connectors-844bdd8f96fa)
