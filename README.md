# installation-grafana
**This is the instruction for beginners who want to install Grafana on PC locally from its latest Docker image**

Here I give you an example for instalattion on Ubuntu 18.04

Using Linux console,write these commands:

**Step 1.** Firstly, we should directly install Docker: 

<code> sudo apt-get update </code>

<code> sudo apt-get install docker.io</code>

**Step 2.** Then we download the docker Grafana image from the online repository:

<code> docker pull grafana/grafana:latest</code>

Also we can check Docker images that are already installed, using:

<code>sudo docker images</code>

![Docker images](https://github.com/shmyaksi/installation-grafana/raw/master/img1.jpg)

**Step 3.** Create folders and set the correct resolution:

<code>sudo mkdir /var/lib/grafana -p</code>

<code>sudo chown -R 472:472 /var/lib/grafana</code>

**Step 4.** After that we run the new Docker container, using installed Grafana image:

<code>sudo docker run -d -p 3000:3000 -v /var/lib/grafana:/var/lib/grafana -e "GF_SECURITY_ADMIN_PASSWORD=YOURPASSWORD" grafana/grafana</code>

!!This is your information to sign in: admin "admin" and password that you set by yourself!!

That command will return your Grafana ID,save it.

![Grafana ID](https://github.com/shmyaksi/installation-grafana/raw/master/img2.jpg)

**Step 5.** After Grafana is installed on your server, open your web-browser and type the grafana server IP address (with port 3000) in the following way.

http://localhost:3000/

Log in to the Grafana Dashboard using default user 'admin' and your password.(Or a default password 'admin'.In this case, you will be proposed to change the password.)

You will see Grafana as shown below:
![Grafana](https://github.com/shmyaksi/installation-grafana/raw/master/image1.jpg)

**Step 6.** Then we need to create a new Dashboard: 

![Grafana](https://github.com/shmyaksi/installation-grafana/raw/master/image12.jpg)

**Step 7.** Add Query TestData DB and finally we get the first dashboard:

![Grafana](https://github.com/shmyaksi/installation-grafana/raw/master/image2.jpg)


With another query scenario:


![Grafana](https://github.com/shmyaksi/installation-grafana/raw/master/image4.jpg)



