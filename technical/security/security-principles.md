# Security Principles  

## AWS

The AWS cloud platform operates on a [shared responsibility model](https://aws.amazon.com/compliance/shared-responsibility-model/). This means that we are still responsible for security within our cloud, just as we would be if we were using an on-site data centre.

The [principle of least privilege](https://en.wikipedia.org/wiki/Principle_of_least_privilege) should be applied where appropriate. That is do not give blanket access - instead, invert the model such that access is not allowed by default and must be allowed.

### Security group open to unauthorized ports

A commonly `noncompliant` resource is a `security group` which exposes inbound traffic from unauthorised ports. This is an issue for a few different reasons. Allowing public access means any hacker that compromises your instance can then use it to try and pivot through other AWS machines and into things they definitely shouldn’t have access to. They could also use it for cryptocurrency mining, bulk spamming emails, and much much more.

If we want to connect to an EC2 instance using `ssh`, we must allow inbound traffic to port `22`. Instead of allowing all `ssh` traffic from all IPv4 addresses (i.e. `0.0.0.0/0`), we can specify only the necessary addresses. For example, we could allow traffic only from certain range of IP addresses.
