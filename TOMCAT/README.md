# APACHE TOMCAT & HOSTING A JAVA APPLICATION ON TOMCAT

Apache is an open-source application-based web server. It allows client-server interaction to run smoothly. From processing request for images, videos, texts, etc and bundling it into browser compatible format before being displayed to the user.

In this section, I will be learning how to setup a web server on a virtual machine. By incorporating the knowledge from the previous section (Maven), I will be using MAVEN to package a java web application into a .war file which we are going to deploy on the Apache web server. The result of this will be a webpage that we can access via `localhost:8080`

```
Summary

1. Create a server
2. Use Maven to package the java application into a .war file
3. Move the package into the server
4. Run and access the webpage via port 8080

```

## Setting Up Apache TOMCAT

For the webserver, we will be using TOMCAT because our application is a Java-based app. Example of other servers include: NGINX, Apache HTTPS server.

### Pre-requisite

- set up a Ubuntu VM or AWS ubunu EC2 instance
- Learn basic linux commands
- Basic understanding of Maven setup and commands
- A cup of cold milk/tea/coffee/soda

### Step 1: Downloading Apache

create an opt folder and change the directory into the folder

`cd /opt`

Now download the tomcat as tar.gz folder.

`sudo wget https://archive.apache.org/dist/tomcat/tomcat-9/v9.0.65/bin/apache-tomcat-9.0.65.tar.gz`

This folder is in a somewhat zip file. We will need to unzip it.

`sudo tar -xvf apache-tomcat-9.0.65.tar.gz`

now cd into the extracted folder and navigate to /conf folder. You might need to change permission to -rw.

```
cd apache-tomcat-9.0.65
cd conf

```

Now edit the tomcat-users.xml file inside the 'conf' folder

`vi tomcat-users.xml`

What are we doing here? we need to add user details to the user list.

```
    <!-- copy and paste the code below into second to the last line -->
    <user username="admin" password="admin1234" roles="admin-gui, manager-gui"/>
    <!-- You can change the username and password if you want -->

```

This line of code is just adding a new user whose role could be admin or manager.

We will need to remove/comment out the code below from the the `context.xml` located in these two folders: `apache-tomcat-9.0.65/webapps/manager/META-INF` and `apache-tomcat-9.0.65/webapps/host-manager/META-INF`

```
<!-- find this line of code and comment it out / or remove it completely -->
    <!-- Valve className="org.apache.catalina.valves.RemoteAddrValve" allow="127\.\d+\.\d+\.\d+|::1|0:0:0:0:0:0:0:1" /> -->
```
