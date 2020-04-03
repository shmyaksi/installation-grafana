# installation-grafana
**This is the instruction for beginners who want to install Grafana on PC locally from its latest Docker image**

Here I give you an example for instalattion on Ubuntu 18.04
Using Linux console,write these commands:
**Step 1.** Firstly, we should directly install Docker: 
- sudo apt-get update
- sudo apt-get install docker.io
**Step 2.** Then we download the docker Grafan image from the online repository:
-docker pull grafana/grafana:latest
Also we can check Docker images that are already installed, using:
- sudo docker images
![Docker images](https://github.com/shmyaksi/installation-grafana/raw/master/img1.jpg)

**Step 3.** Create folders and set the correct resolution:
- sudo mkdir /var/lib/grafana -p
- sudo chown -R 472:472 /var/lib/grafana

After that we run the new Docker container, using installed Grafana image:
- sudo docker run -d -p 3000:3000 -v /var/lib/grafana:/var/lib/grafana -e "GF_SECURITY_ADMIN_PASSWORD=YOURPASSWORD" grafana/grafana
!!This is your information to sign in: admin "admin" and password that you set by yourself
After that command you'll get the Grafana ID,save it.

![Grafana ID](https://github.com/shmyaksi/installation-grafana/raw/master/img2.jpg)

