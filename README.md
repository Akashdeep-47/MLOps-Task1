# Master Development Environment
A task of integrating docker, jenkins, git and github.

---

# JOB#1
If Developer push to dev branch then Jenkins will fetch from dev and deploy on dev-docker environment.

---

# JOB#2
If Developer push to master branch then Jenkins will fetch from master and deploy on master-docke environment.
both dev-docker and master-docker environment are on different docker containers.

---

# JOB#3
Manually the QA team will check (test) for the website running in dev-docker environment. If it is running fine then Jenkins will merge the dev branch to master branch and trigger #job 2

---

# Docker
Docker is a tool designed to make it easier to create, deploy, and run applications by using containers. Containers allow a developer to package up an application with all of the parts it needs, such as libraries and other dependencies, and deploy it as one package. By doing so, thanks to the container, the developer can rest assured that the application will run on any other Linux machine regardless of any customized settings that machine might have that could differ from the machine used for writing and testing the code.

---

# Jenkins
Jenkins is an open-source automation tool written in Java with plugins built for Continuous Integration purposes. Jenkins is used to build and test your software projects continuously making it easier for developers to integrate changes to the project, and making it easier for users to obtain a fresh build. It also allows you to continuously deliver your software by integrating with a large number of testing and deployment technologies.

With Jenkins, organizations can accelerate the software development process through automation. Jenkins integrates development life-cycle processes of all kinds, including build, document, test, package, stage, deploy, static analysis, and much more.

Jenkins achieves Continuous Integration with the help of plugins. Plugins allows the integration of Various DevOps stages. If you want to integrate a particular tool, you need to install the plugins for that tool. For example: Git, Maven 2 project, Amazon EC2, HTML publisher etc.

---

# Git and Github
Git is essentially a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.

In other words:

It allows groups of developers to collaborate on the same documents (often source code) simultaneously and without overriding each other’s work. 

GitHub allows developers to host their files in a ‘Git Repository’ so that other people can collaborate on projects with them, whether they are open for public contribution (open source) or closed for specific colleagues to work on a private project. The idea is not dissimilar to the way Google Docs lets you host your word processing and spreadsheet files and opens them up for collaboration, though developers do not work on the same documents together in real time or make changes directly in the browser.
