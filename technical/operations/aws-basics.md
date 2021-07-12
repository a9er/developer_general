# AWS Basics  

AWS is one of the most popular cloud providers that currently exist on the web. AWS allows for resources to be allocated with simple API calls - allowing developers to create applications that are ready for production or large-scale traffic almost immediately.

The world of AWS is a big one, but here's a couple of important bits that you'll need to know about:

## The Basics

[EC2 Instances](https://aws.amazon.com/getting-started/tutorials/launch-a-virtual-machine/) allow you to run a virtual 'computer' in the cloud - with the same attributes as any computer you can install operating systems on.

[RDS Databases](https://aws.amazon.com/getting-started/tutorials/create-mysql-db/) let you make a relational database (say, MySQL or PostgeSQL) where the management of snapshots and backups is fully managed by AWS.

[Route 53](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/getting-started.html) lets you delegate a DNS record that you own to your resources. Remember DNS earlier? This lets you direct requests to a domain name of your own to go to your instance.

## Checkpoint: Exercise 1

Create a simple website with EC2 instances, and forward traffic to it using a Route53 Hosted Zone.

## Advanced

[VPC](https://docs.aws.amazon.com/AmazonVPC/latest/GettingStartedGuide/ExerciseOverview.html) lets you make your inter-application traffic 'private' - in that it does not traverse the public internet. This is critical to the security of the apps that you deploy to the cloud.

[Cloudformation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/GettingStarted.Walkthrough.html) lets you create almost every AWS resource with file declarations - which means that you gain repeatable, predictable infrastructure. This means that the infrastructure that you need can be deployed in seconds, and will be the same infrastructure with no variations.

## Checkpoint: Exercise 2

That EC2 instance you backed with Route53? Now try declaring the whole thing with Cloudformation.

## Clean up

All done? Nice one! 

When you have finished, don't forget to delete any resources you have created in the AWS account. This will free up some space for your fellow Proteges to create their own resources for learning. It also saves money $$ 

If you think you may want to create similar resources in the future, just make a note of what you did before deleting anything. If you have declared the whole thing in Cloudformation then you should already have a very good record of what you have done.  

### But what about my quorum? 
If you'd like to keep your resources up while you prepare for your quorum, that's completely fine. Just clean them up once your quorum is done and dusted. 
