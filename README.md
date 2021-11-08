# M21CS060

Steps followed for successful completion of Dockerizing web application.</br>
</br>
The web application has only 2 html webpages, interlinked with each other.</br>
Names being: index.html, answers.html.</br>
Operating System used: Ubuntu 20.04.3 LTS.</br>
Server used: nginx server.</br>
localhost port was changed to 8000, and was mapped with the nginx default port of 80.</br></br>

Terminal commands:</br>
</br>
Installation of docker using software repo:</br>
-> sudo apt install docker.io</br>
check the version of docker:</br>
-> sudo docker --version</br>
check status of docker:</br>
-> sudo systemctl status docker</br>
</br>
search for nginx docker image:</br>
-> sudo docker search nginx</br>
select the official docker image:</br>
-> sudo docker pull docker.io/nginx</br>
</br>
display the running dockers:</br>
-> sudo docker ps</br>
find docker image running succesfully and can stop it run using docker stop command.</br> 
</br>
create a new directory that stores the html pages, and name it nginx-html</br>
-> mkdir ~/nginx-html</br>
-> sudo gedit index.html</br>
-> sudo gedit answers.html</br>

To copy the files present in the nginx-html(on ubuntu), into the docker container(nginx container), use the command</br>
-> sudo docker run -d -p 8000:80 -v ~/nginx-html:/usr/share/nginx/html --name my-nginx nginx</br>

explaination of the command:</br>
here the docker image is my-nginx.</br>
-p 8000:80 - enables the webpages to be locally hosted on port:8000, and maps this to the default nginx port:80</br>
~/nginx-html - location of the file nginx-html, that contains the html pages.</br>
/usr/share/nginx/html - location in the nginx continer, where these files will be stored.</br>
</br>
after executing the above command, check the page using any web browser using: "localhost:8000/" in the url.</br>
