# CI/CD with Containers Kata

The focus of the CI/CD with Containers kata is to put into practice the principles of safety, consistency and reliability in our deployment (that's production!) environments. 

To achieve consistency and reliability, we will lean on container technology (specifically Docker). Your job is to make a reliable pipeline that can deploy your system into production. You are going to use containers as a tool to do this. 

This kata is broken up into three parts. Part 1 focusses around getting a container to run on your local machine. Part 2 focusses around continuous integration, Part 3 focuses on continuous deployment. 

## Containerization

You need to set up a container that your system can be built and run in. It should...

* Have a reliably consistent environment
* Be defined in code
* Be testable in multiple environments (locally and in prod)

## Continuous Integration 

Now that you have a reliable and consistent environment it's time to create a continuous integration pipeline. Your pipeline needs to...

* Be automated (no manual steps)
* Be in version control, automation and pipeline scripts should be treated as first class code citizens
* Triggered on check in to your version control repository, your test suit should run when a commit is made to the repository  

## Continuous Deployment

Now that you have continuous integration working, it's time to implement continuous deployment. 

* Your deployment pipeline needs to be automated (no manual steps)
* If after check in your tests pass the system should be deployed to production
* If after check in one or more of your tests fail the system should **not** be deployed to production

## Clean up
All done? Nice one! When you have finished, don't forget to delete any resources you have created.  

* Maybe you created a pipeline in Buildkite or some resources in AWS. Go ahead and delete these as it will free up some space for your fellow Proteges to create their own resources for learning. It also saves money $$ 
* If you think you may want to create similar resources in the future, just make a note of what you did before deleting anything. If you have declared your pipeline or infrastructure in code then you should already have a very good record of what you have done. 
* If you have finished with your Github repo, archive it.  
