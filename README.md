# M21CS060

Steps followed for successful completion of Dockerizing web application.

The web application has only 2 html webpages, interlinked with each other.
Names being: index.html, answers.html.
Operating System used: Ubuntu 20.04.3 LTS.
Server used: nginx server.
localhost port was changed to 8000, and was mapped with the nginx default port of 80.

Terminal commands:

Installation of bash using software repo:
-> sudo apt install docker.io
check the version of docker:
-> sudo docker --version
check status of docker:
-> sudo systemctl status docker

search for nginx docker image:
-> sudo docker search nginx
select the official docker image:
-> sudo docker pull docker.io/nginx

display the running dockers:
-> sudo docker ps
find docker image running succesfully and can stop it run using docker stop command. 

create a new directory that stores the html pages, and name it nginx-html
-> mkdir ~/nginx-html
-> sudo gedit index.html
-> sudo gedit answers.html

To copy the files present in the nginx-html(on ubuntu), into the docker container(nginx container), use the command
-> sudo docker run -d -p 8000:80 -v ~/nginx-html:/usr/share/nginx/html --name my-nginx nginx

explaination of the command:
here the docker image is my-nginx.
-p 8000:80 - enables the webpages to be locally hosted on port:8000, and maps this to the default nginx port:80
~/nginx-html - location of the file nginx-html, that contains the html pages.
/usr/share/nginx/html - location in the nginx continer, where these files will be stored.

after executing the above command, check the page using any web browser using: "localhost:8000/" in the url.
