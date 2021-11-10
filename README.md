Part-I

Installation Process & setup of Docker
i. Go to DockerHub copy the ink , after that back to RHEL8
ii. In rhel8 go to the directory /etc/yum.repos.d using these cmd:
"cd /etc/yum.repos.d"
iii. After that create a file for any name in my condition i create a file that is docker1.repo
in this file i write the code as like
[docker]
baseurl = url
gpgcheck=0
iv. After that save the file and run the cmd:
"gpgcheck=0"
v. for updating the repolist i run the cmd:
"yum repolist"
vi. Then for installation of docker run the cmd:
"yum install docker-ce --noobest"
vii. After instalation cheked it is installed or not run the cmd:
"rpm -q docker-ce"
viii. After that for starting the service run the cmd:
"systemctl start docker"
ix. For checking it is started or not run the cmd:
"systemctl status docker"
x. After that for running alll time docker services run the cmd:
"systemctl enable docker"

Now the start the process of part-I
i. Pull the both images using these cmd:
"docker pull infracloudio/csvserver:latest"
"docker pull prom/prometheus:v2.22.0"
ii. After that create a file for InputFile and giving the given data
iii. After that create a bash Script as a name gencsv.sh for creating the bash script run the cmd:
"gedit gencsv.sh" And make the file executable use the cmd:
"chmod a+x gencsv.sh"
iv. After that run the script for 10 entries in InputFile
v. Launch the docker container in background with the help of given pulled image cmd as like:
"docker run -dit --name infra21 infracloudio/csvserver:latest"
vi. copy these things that done in previousely
vii. For checking the which port is listening run the cmd:
"ps -aux"
viii. After that stopping the container use the cmd:
"docker stop infra21"
ix. for deleting that container i used the cmd:
"docker rm -f infra21" -f used for forcefully
x. for connecting with the given host i first installing the server Apache server useing these cmd:
"Yum install --net-tools -y"
"yum install httpd -y"
xi. After installation start the service using these cmd:
"systemctl start httpd"
"systemctl status httpd"
"systemctl enable httpd"
xii. After that change the port no. of HTTP that is 80 to 9393 for connecting the localhost server. using these cmd:
"netstat -tnlp"
"kill port"
"ps -aux"
"httpd
"ps -aux"
"netstat -tnlp"

Part-II
i. Delete all the container running using the cmd:
"docker rm -f $(docker ps -a -q)"
ii. After that create a yaml file using these cmd:
"docker-compose.yaml"
iii. Write the which is mentioned in file
iv. After this run the file using these cmd:
"docker-compose up -d"

Part-III
i. Delete all the container which is running in previousely using the cmd:
"docker rm -f $(docker ps -a -q)"
ii. Go to that yaml file and changes the image and put prom/prometheus:v2.22.0
iii. And run the yaml file
iv. After running the cmd container launched and for connecting with the localhost firstly install the httpd server
and change the port no and give the port no. which is mentioned in localhost.
