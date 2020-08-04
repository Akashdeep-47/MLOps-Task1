# Master Development Environment
A task of integrating docker, jenkins, git and github.

---


## Docker
Docker is a tool designed to make it easier to create, deploy, and run applications by using containers. Containers allow a developer to package up an application with all of the parts it needs, such as libraries and other dependencies, and deploy it as one package. By doing so, thanks to the container, the developer can rest assured that the application will run on any other Linux machine regardless of any customized settings that machine might have that could differ from the machine used for writing and testing the code.

---


## Jenkins
Jenkins is an open-source automation tool written in Java with plugins built for Continuous Integration purposes. Jenkins is used to build and test your software projects continuously making it easier for developers to integrate changes to the project, and making it easier for users to obtain a fresh build. It also allows you to continuously deliver your software by integrating with a large number of testing and deployment technologies.

With Jenkins, organizations can accelerate the software development process through automation. Jenkins integrates development life-cycle processes of all kinds, including build, document, test, package, stage, deploy, static analysis, and much more.

Jenkins achieves Continuous Integration with the help of plugins. Plugins allows the integration of Various DevOps stages. If you want to integrate a particular tool, you need to install the plugins for that tool. For example: Git, Maven 2 project, Amazon EC2, HTML publisher etc.

---


## Git and Github
Git is essentially a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.

In other words:

It allows groups of developers to collaborate on the same documents (often source code) simultaneously and without overriding each other’s work. 

GitHub allows developers to host their files in a ‘Git Repository’ so that other people can collaborate on projects with them, whether they are open for public contribution (open source) or closed for specific colleagues to work on a private project. The idea is not dissimilar to the way Google Docs lets you host your word processing and spreadsheet files and opens them up for collaboration, though developers do not work on the same documents together in real time or make changes directly in the browser.

---


## JOB => 1
If Developer push to dev branch then Jenkins will fetch from dev and deploy on dev-docker environment.

- Setting up the development environment.

  ![Alt text](https://github.com/Akashdeep-47/mlops_task1/blob/master/Job1/Screenshot%20(223).png)


- Adding the Github link of the task. Also don't forget to add your Github Credentails fro allowing Jenkins to access the Github task repo. Also you can clearly see that Branch Specifier i.e dev branch which means its a development branch.

  ![Alt text](https://github.com/Akashdeep-47/mlops_task1/blob/master/Job1/Screenshot%20(224).png)

- Further you can use any build trigger. Its only use case is to how you want to start your job. Here, I have used the Poll SCM. 
  You can use of your choice.
  
  - Now adding the command to the execute shell.
  ```
  sudo cp -r -f -v * /root/dev
  if sudo docker ps | grep job1
  then
  echo "Already running"
  else
  sudo docker run -dit -p 8085:80 -v /root/dev:/usr/local/apache2/htdocs/ --name job1 httpd
  fi
  ```
    ![Alt text](https://github.com/Akashdeep-47/mlops_task1/blob/master/Job1/Screenshot%20(225).png)
  
  Here, I have been using RHEL8 as my opertaing system, that's why using the execute shell.
  Now, copying the file from Github repo to the loaction /root/dev. You can give of your choice and then launching the docker container of httpd webserver having the  dev branch file.
  
- Finally my development job runned successfully.
  
  ![Alt text](https://github.com/Akashdeep-47/mlops_task1/blob/master/Job1/Screenshot%20(226).png)
  
  ---


## JOB => 2
If Developer push to master branch then Jenkins will fetch from master and deploy on master-docke environment.
both dev-docker and master-docker environment are on different docker containers.
  
- Setting up the production environment.

  ![Alt text](https://github.com/Akashdeep-47/mlops_task1/blob/master/Job2/Screenshot%20(227).png)


- Adding the Github link of the task. Adding credentails is one time process so not needed here. Also you can clearly see that Branch Specifier i.e master branch which means its a production branch.

  ![Alt text](https://github.com/Akashdeep-47/mlops_task1/blob/master/Job2/Screenshot%20(228).png)

- Similarily to the preious job you can use any build trigger. Here, I have also used the Poll SCM. 
  
  - Now adding the command to the execute shell.
  ```
  sudo cp -r -f -v * /root/master
  if sudo docker ps | grep job2
  then 
  echo "Already running"
  else
  sudo docker run -dit -p 8084:80 -v /root/master:/usr/local/apache2/htdocs/ --name job2 httpd
  fi
  ```
    ![Alt text](https://github.com/Akashdeep-47/mlops_task1/blob/master/Job2/Screenshot%20(229).png)
  
  Similarily, to the previous job copying the file from master branch to some local location and then further launching the docker container of httpd webserver having the   master branch file.
  
  - Finally my production job runned successfully.
  
  ![Alt text](https://github.com/Akashdeep-47/mlops_task1/blob/master/Job2/Screenshot%20(230).png)
  
  ---
  
  
 ## JOB = >3
Manually the QA team will check (test) for the website running in dev-docker environment. If it is running fine then Jenkins will merge the dev branch to master branch and trigger #job 2

- Setting up the production environment.

  ![Alt text](https://github.com/Akashdeep-47/mlops_task1/blob/master/Job3/Screenshot%20(231).png)
  
- Adding the Github link of the task. Also you can clearly see that Branch Specifier i.e dev branch as we will be going to merge the dev environment to the master environment if dev environment works fine.

  ![Alt text](https://github.com/Akashdeep-47/mlops_task1/blob/master/Job3/Screenshot%20(232).png)
  
  - This time adding some additional behaviour i.e merging the dev branch to master branch.
  
    ![Alt text](https://github.com/Akashdeep-47/mlops_task1/blob/master/Job3/Screenshot%20(233).png)
  
   Here, the option are moreover clear what to choose. Rest all things remain set to default.
   
- Finally mergering job also runned successfully.
  
  ![Alt text](https://github.com/Akashdeep-47/mlops_task1/blob/master/Job3/Screenshot%20(235).png)
  ![Alt text](https://github.com/Akashdeep-47/mlops_task1/blob/master/Job3/Screenshot%20(236).png)
  
---


## Contributing
Pull requests are welcome. Feel free to give suggestion.
   
   


  
