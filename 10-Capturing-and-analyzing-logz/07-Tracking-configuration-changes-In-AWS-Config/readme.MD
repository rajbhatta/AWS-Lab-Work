# 1. Tracking configuration changes in AWS Config #
-  Suppose that an IT auditor comes to you one day and she says please give me a record showing the current configuration state of all your AWS services. 

- How would you do that? Well, you could go through each service and manually document the configuration, and you would probably be doing that for a week straight. 

- Okay, but now suppose that the auditor says, by the way, please also give me a list of all changes that occurred in the AWS environment and when those changes occurred. 

- Now almost reflexively, you might think I'll just give her the CloudTrail Logs. And you could do that, but it actually would not be enough. 

- See, CloudTrail tracks who accessed or made a change to a resource. For example, suppose that you created a CloudWatch alarm one month ago. Obviously that action caused the alarm to exist. Today someone, not you, of course, someone else, deleted that alarm, causing the alarm to cease to exist. 

- Now CloudTrail would log these events. It would tell you the actions that took place, who performed the actions, and when. But suppose the auditor asks you about the state of the alarm as of two weeks ago. 

- Now CloudTrail Logs would not explicitly tell you when that alarm existed. Two weeks ago, there were no actions that took place against the alarms, so there was nothing for CloudTrail to log. 

- You would have to sort through the logs to correlate the events that took place with the state of the CloudWatch alarm configuration two weeks ago. Now that is not too difficult to do for one resource, but it's pretty much impossible with hundreds or thousands of resources unless you automate it. 

- And that is where AWS Config comes in. Config tracks what a service configuration looked like at a point in time. Whereas, CloudTrail is concerned with the specific activities that occurred with a service, AWS Config is concerned with the end result of those activities. 

- Think of AWS Config as a time machine. You can use it to see what a configuration looked like at some point in the past versus what it looks like now. 

- Now AWS Config does three basic things. As I said, it monitors for changes to resources, and you can choose to monitor all resources or specific ones. It keeps a record of those changes in an S3 bucket, and it can optionally send SNS notifications when a resource changes. 

