# CI/CD

### What is it?

It is a method in which some of the processes are automated to deliver a product more efficiently and more frequently.  `Continous Integration` is when all members of the team continously integrate their work into a single repository.  `Continuous Delivery` is when enough automation from the integration part of the system has been successfully tested to the point where the product can be continuously delivered. `Continuous Deployment` is when the process of continous delivery can be automated.  This makes things more efficient, but sometimes it is preferable to use continuous delivery.  For example, if there is more time, you may want to deliver after checking first, in which case delivery would be preferable.

NOTE: CI/CD is considered the backbone of DevOps.

----

### Why is it so useful?

It is popular in DevOps because it makes things more efficient with less human errors and ultimately speeds everything up.  It makes it easier to spot and fix bugs.

----

### Jenkins: what is it?

(info from medium.com)

- Jenkins is an open source CI/CD tool written in Java

- It has a lot of plugins available

- It provides a feedback loop to fix errors

- It helps advance the SDLC (software development life cycle) faster through automation

NOTE: the SDLC = plan - design - develop - test - deploy


----

### Jenkins process

![alt](jenkins.jpg)

In order for the continuous integration stage to happen smoothly, it is required that all members of the team continuously push the code that they have tested into a single repository.

You can set up a notification system on GitHub to automatically inform people when a new change has been pushed onto the shared repo. This is called a `webhook trigger`.

You can use Jenkins to automatically test code, and once the code has passed the test, the Master Node can send it to production, otherwise, it will go from Agent Node back to wherever the issue lies, and the process repeats.

Once the code is suitable for deployment, it can be passed to Amazon Web Services for `continuous delivery`.

If this stage can be automated, it will have reached `continuous deployment`.

You always want to deploy manually first!

You will need ssh keys to show that you have the required permissions for all of these stages.

You can use the `scp` command to get your app onto AWS via your Jenkins ssh key.

E.g. `scp -i "~/.ssh/tech230.pem" -r app ubuntu@ec2-<ip address of your instance>.eu-west-1.compute.amazonaws.com:/home/ubuntu`

You won't deploy the app until you start the process.  I.e. `npm start`.

You want to be careful deploying, as once it's done, there is no way back and the public can reach it.

----

### Jenkins stages and steps

(info from cloudaffaire.com)

`Stages` contain `stage directives`

`Stage directives` contain `steps`

`Steps` are actions that you want to perform in your Jenkins' pipeline.

----

### Alternatives to Jenkins

Alternatives to Jenkins include:

- GitLab
- Atlassian Bamboo
- CircleCI
- TeamCity
- Travis CI
- BuildMaster

----

