# Managing Secrets

## What is a secret?

A secret is "something" that could be used to authenticate against "something else".

For example, your company password is a secret because when used in combination with your email, someone could login as you to internal products / services. You wouldn't share your password with others, but to receive emails from others, you would share your email. That makes your email "sensitive", in which you may want to be selective with who you share you email with.

Some common examples of secrets are:

* Credentials.
> Could be a password, sometimes both a username & password. A pair of access key ID and secret access key.
* API tokens.
> Used to authenticate against an API. Some common services which use these tokens include GitHub, Slack, TeamCity, Jenkins and so on. 
* SSH keys.
> Used to authenticate to remove servers and service.
> You may use this already to authenticate when pushing code to GitHub. If you're unsure if you're using SSH keys, see [this page](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/checking-for-existing-ssh-keys) from GitHub.
* \+ more.

## Where should secrets be stored?

Some common places to store secrets are:

* a password management service such as lastpass or 1Password ([see the official 1Password docs on how to store secrets](https://support.1password.com/getting-started-mac/)).

* AWS SSM Parameter Store ([see the AWS SSM Parameter Store example below.](#example---aws-ssm-parameter-store)).

## How do I share secrets with others?

**What you shouldn't do:**

* Share a secret with someone over Slack or Microsoft Teams or Google Hangout or etc.
    * Slack, Microsoft Teams and Google Hangout are tools for communication in channels (both public and private). These channels can be searched and could be viewable to employees of those companies.

* Send a secret via email.
    * The emails for a user can still be accessed when they leave the company, so any secrets exposed could be used if they are not changed / revoked after a user leaves the company. Emails can also be forwarded without the original sender’s knowledge, which means your secret could be shared without you knowing.

**What you should do:**

* Add the secret to a lastpass/1Password vault shared with your team.
    * This allows anyone in your team to see the secret whenever they need to. 1Password as a business is paid specifically for this service, so they incorporate an extra level of care to ensure their employees can't access secrets.

* Add your secret to AWS SSM Parameter Store, if the secret is related to an application running in AWS.
    * This allows anyone with access to that AWS account to pull the secret and will require additional permissions for your application to pull from there.
    * [See the AWS SSM Parameter Store example below for how to use this.](#example---aws-ssm-parameter-store)

* Share the secret directly with someone using PrivateBin or SnapPass.
    * This allows a secret to be shared securely between two parties, where once a secret is viewed it can't be view again without creating a new message. 

## How do I expose a secret to my application?

**What you shouldn't do:**

* Store your secret in line within your code.
```C#
string token = "xxxx"
```

This would expose your token in your source code, if committed, and could be found in the git commit history for your project. If you were to push this to a public GitHub repository, for example, anyone on the internet would be able to find and view your secret.

**What you could do instead:**

Using your terminal, expose your secret to your local environment by running:
```bash
export MY_SECRET=xxxx
```

Then in your application, add the following to pull the secret from your local environment.

```C#
string token = Environent.GetEnvironmentVariable("MY_SECRET")
```

This means that the secret is only exposed to your local environment and read into your application via _environment variables_ at runtime, where the value for `token` can be seen in memory only.

> Ideally basic validation would be implemented to check if `token` has a value, depending on your application or what you're trying to do with the value.

---

**What you shouldn't do:**

* Output the contents of token as part of your logs.

```C#
string token = "xxxx";
Console.WriteLine(token);
```

While it is okay to do this during local development and testing, if you forgot to remove lines like this once your application starts logging to a place other than your local machine, it could expose your secret somewhere where someone could use it. Be conscientious of where your application logs are being output.

## Example - AWS SSM Parameter Store

> [Official docs](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-parameter-store.htm) | [Link to AWS SSM Parameter Store in AWS Console](https://console.aws.amazon.com/systems-manager/parameters)

AWS SSM Parameter Store is a key value store used to store secrets in an AWS Account. It supports 3 types of values which can be stored:

1. String
    * a single basic string (eg. `this is my secret`, or `12345`)
2. StringList.
    * a comma seperated list of strings (eg. `this,is,my,secret`)
3. SecureString.
    * a single basic string that is encrypted by AWS KMS. Ideally this should be used for secrets.

---

**Please Note:**

The below examples are for putting and pulling parameters from AWS SSM Parameter Store using the terminal. If you're looking to pull your parameters into your application, [AWS will likely provide an SDK for you to use](https://docs.aws.amazon.com/cdk/latest/guide/get_ssm_value.html).

---

**Prerequisites:**
* Have `awscli` installed (used run queries against your authed AWS Account).
    * [See the official docs for an installation guide](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv1.html)).
* You might need a company authentication client. e.g. saml2aws.

To add a token to AWS SSM Parameter Store, using a terminal, run:

```bash
# for a String type.
aws ssm put-parameter --name "/the/path/i/want/for/my/token" --value "this is my secret" --type String

# for a StringList type.
aws ssm put-parameter --name "/the/path/i/want/for/my/token" --value "this is my secret" --type StringList

# for a SecureString type, using the default KMS key for an AWS account.
aws ssm put-parameter --name "/the/path/i/want/for/my/token" --value "this is my secret" --type Securestring
```

To retrieve a token from AWS SSM Parameter Store, using a terminal, run:

```bash
# for all types (a SecureString type will return an entrypted value).
aws ssm get-parameter --name "/the/path/i/want/for/my/token"

# for a SecureString type, with an unencrypted value.
aws ssm get-parameter --name "/the/path/i/want/for/my/token" --with-decryption
```
You'll notice that the output of `aws ssm get-parameter` is in JSON format. To retrieve just the output for the `value` field in the payload, add `--query 'Parameter.Value' --output text` to those queries.

```bash
# for example
aws ssm get-parameter --name "/the/path/i/want/for/my/token" --value "this is my secret" --type String --query 'Parameter.Value' --output text
```

### Tips

* You can run `aws ssm describe-parameters` to retrieve a list of ALL the parameters currently stored in your authed AWS account. This will only output the path of the parameter, and not the value of the parameter itself.

* You can use `aws ssm delete-parameter --name "/the/path/i/want/for/my/token"` to remove a parameter from AWS SSM Parameter Store. Be sure to double check the `--name` value given is correct, so you don't accidentally remove a parameter you don't want to remove.