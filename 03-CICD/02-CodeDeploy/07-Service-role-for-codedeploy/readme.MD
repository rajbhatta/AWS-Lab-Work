# What is service role for codeDeploy ? #
- In AWS, service roles are used to grant permissions to an AWS service so it can access AWS resources. The policies that you attach to the service role determine which resources the service can access and what it can do with those resources.

- The service role you create for CodeDeploy must be granted the permissions required for your compute platform. If you deploy to more than one compute platform, create one service role for each. To add permissions, attach one or more of the following AWS supplied policies:

- For EC2/On-Premises deployments, attach the <b>AWSCodeDeployRole policy </b>. It provides the permissions for your service role to:

- Read the tags on your instances or identify your Amazon EC2 instances by Amazon EC2 Auto Scaling group names.
- Read, create, update, and delete Amazon EC2 Auto Scaling groups, lifecycle hooks, and scaling policies.
- Publish information to Amazon SNS topics.
- Retrieve information about CloudWatch alarms.
- Read and update Elastic Load Balancing.


# Reference #
- https://docs.aws.amazon.com/codedeploy/latest/userguide/deployment-groups-create-in-place.html