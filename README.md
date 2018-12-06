# build-help-portal
Compiled help portal files to be used for creating final output

To generate html from markdown available in content-help-portal and push it to the help-portal git repo

* cd mdhtml/
* sudo docker build --build-arg GITHUB_TOKEN=YOURTOKENHERE --build-arg GITHUB_USERNAME=YOURUSERNMAME --build-arg GITHUB_EMAIL=YOURMEMAIL@DOMAIN.com -t build-help-site  .  


To Host the help-portal on an apache webserver

* cd apache/
* sudo docker build --build-arg GITHUB_TOKEN=YOURTOKENHERE --build-arg GITHUB_USERNAME=YOURUSERNMAME --build-arg GITHUB_EMAIL=YOURMEMAIL@DOMAIN.com -t help-site  .  
* sudo docker run -dit --name host-help-site-running -p 8080:80 host-help-site  