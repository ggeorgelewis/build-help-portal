# build-help-portal

* The dockerfile in md2html/ pulls the markdown from the content-help-site git repo and pushes the generated html to help-site git repo

* The dockerfile in apache/ creates a container with the help-site content pulled from git to enable the website to be accessible at port localhost:8080

##PROCESS

* Install Docker
  * https://docs.docker.com/install/linux/docker-ce/ubuntu/#prerequisites


* Clone the Build Help Portal repository
  * https://github.com/ggeorgelewis/build-help-portal.git   

* Execute the build process that generates help-site html from markdown available in content-help-portal and pushes it to the help-portal git repo

  * cd mdhtml/
        * sudo docker build --build-arg GITHUB_TOKEN=YOURTOKENHERE --build-arg GITHUB_USERNAME=YOURUSERNMAME --build-arg GITHUB_EMAIL=YOURMEMAIL@DOMAIN.com -t build-help-site  .  

* To Host the help-portal on an apache webserver build the apache/dockerfile to create a container hosting the website on apache ubuntu
    
  * cd apache/

      * sudo docker build --build-arg GITHUB_TOKEN=YOURTOKENHERE --build-arg GITHUB_USERNAME=YOURUSERNMAME --build-arg GITHUB_EMAIL=YOURMEMAIL@DOMAIN.com -t help-site  .  
 
 
 * run the container to make the website accessible
  * sudo docker run -dit --name host-help-site-running -p 8080:80 host-help-site 
 
 
 * Visit the website at http://localhost:8080 or http://serverIP:8080 