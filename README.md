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

<blockquote>Note: it's your data to sign in: type 'admin' in a field "admin" and password that you set earlier
</blockquote>

That command will return your Grafana ID,save it.

![Grafana ID](https://github.com/shmyaksi/installation-grafana/raw/master/img2.jpg)

<blockquote>Also you may need to stop the container, use: 

<code> sudo docker container stop 12345678923</code> where  12345678923 is YOUR container's ID </blockquote>

<blockquote>In case of error, use:

<code> sudo docker container logs 12345678923</code> where  12345678923 is YOUR container's ID </blockquote>

**Step 5.** After Grafana is installed on your server, open your web-browser and type the grafana server IP address (with port 3000) in the following way.

http://localhost:3000/

Log in to the Grafana Dashboard using default user 'admin' and your password.(Or a default password 'admin'.In this case, you will be proposed to change the password.)

You will see Grafana as shown below:
![Grafana](https://github.com/shmyaksi/installation-grafana/raw/master/image1.jpg)

**Step 6.** Click "Add data source and choose "TestData DB"

![Grafana](https://github.com/shmyaksi/installation-grafana/raw/master/image6.jpg)


**Step 7.** Then we need to create a new Dashboard: 

![Grafana](https://github.com/shmyaksi/installation-grafana/raw/master/image12.jpg)

**Step 8.** Choose Query "TestData DB" instead of "default" and finally we get the first dashboard:

![Grafana](https://github.com/shmyaksi/installation-grafana/raw/master/image2.jpg)


With another query scenario:


![Grafana](https://github.com/shmyaksi/installation-grafana/raw/master/image4.jpg)


Don't forget to save your Dashboard in the upper right corner.

And we did it! 

If you have any questions or problems, Grafana will help you:

https://grafana.com/docs/grafana/latest/installation/docker/


