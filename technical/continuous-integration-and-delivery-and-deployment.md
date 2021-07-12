# Continuous Integration / Continuous Delivery / Continuous Deployment

## What is Continuous Integration (CI)?

`Continuous Integration` is a practice where developers regularly merge their code changes back into their source code repository, after which automated builds and tests are run to verify the quality of the changes.

## What is Continuous Delivery / Continuous Deployment (CD)

`Continuous Delivery` is an extension of CI, where developers automate the process for pushing changes directly to production. On top of having automated builds and testing from CI, `Continuous Delivery` aims for developers to have the release process for a product or service automated. However, the timing of when to push it to production is a business decision, so the final deployment is a manual step that triggers an automated process to get the changes to production.

`Continuous Deployment` is virtually identical to `Continuous Delivery`, except there is no manual process when it come to the release to production. The entire process from commit to release is completely automated, so any working valid change goes all the way to production.

Considering `Continuous Delivery` & `Continuous Deployment` are so closely related, the nickname for the entire process is often known as **CI/CD**.

### Common CI/CD solutions
(aka. vendors)

* [Bamboo](https://www.atlassian.com/software/bamboo)
* [GitHub Actions](https://github.com/features/actions)
* [GitLab CI](https://about.gitlab.com/stages-devops-lifecycle/)
* [GoCD](https://www.gocd.org/)
* [Jenkins](https://jenkins.io/)
* [TeamCity](https://www.jetbrains.com/teamcity/)
* [TravisCI](https://travis-ci.org/)
* plus more..

Some of these vendors are paid solutions, and some offer free services you could use in your projects.
* For example, everyone with a GitHub account has access to `2000` minutes per month of using `GitHub Actions`.

## Why use CI/CD?

1. **Automated testing occurs for every change.**
    * You'll encounter less "it works on my machine" issues because you have tests automatically running in a consistent way. No longer will you forget to run tests locally with your new changes!

1. **Increased code coverage.**
    * You can setup your CI/CD pipeline to check your test coverage, where every change will provide visibility on how much higher or lower you test coverage is.

1. **Deploy your code to production with confidence.**
    * Every change is tested to determine quality and "correctness" before being deployed to production, which allows you to be confident your changes are working as expected.

1. **You're focused on features for your product or service, rather than how to get changes to your customers.**
    * Through using a CI/CD pipeline, you're no longer waiting for a script or process to be finished locally before you can commit your changes. Push and be notified whether it passed or failed instead!

1. **Parallelization in CI/CD allows you to build faster.**
    * You're able to split your build processes and tests across multiple machines, making your feedback loop faster.

1. **Make quality decisions around merging faster.**
    * You can communicate between your CI/CD vendor (eg. Buildkite) and source control management platform (eg. GitHub) to notify developers of failing tests before any changes are merged.

1. **By automating how your product or service is released to customers, you essentially have a runbook of how to deploy your product or service manually.**
    * This is very useful for catching up joining team members on how a product or service runs / is released to customers.

## Further Resources

Below are some further resources around CI/CD.

**Blogs:**
* [Agile Alliance - Continuous Integration](https://www.agilealliance.org/glossary/continuous-integrationhttp://)
* [Agile Alliance - Continuous Deployment](https://www.agilealliance.org/glossary/continuous-deployment)
* [Agile Alliance - Lead Time](https://www.agilealliance.org/glossary/lead-time)
* [Puppet - Continuous Delivery Vs. Continuous Deployment](https://puppet.com/blog/continuous-delivery-vs-continuous-deployment-what-s-diff)
* [Atlassian - CI vs CI vs CD](https://www.atlassian.com/continuous-delivery/ci-vs-ci-vs-cd)
* [Thoughtworks - Continuous Integration](https://www.thoughtworks.com/continuous-integration)

**Books:**
* Continuous Delivery Reliable Software Releases Through Build, Test, And Deployment Automation by Jez Humble and David Farley ([more info](https://martinfowler.com/books/continuousDelivery.html))
