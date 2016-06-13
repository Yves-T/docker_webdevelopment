#Set up docker for local web development

Based on this [tutorial](http://blog.osteel.me/posts/2015/12/18/from-vagrant-to-docker-how-to-use-docker-for-local-web-development.html)

## To Create the docker machine with vmwarefusion driver

		#create the docker vm machine
		docker-machine create --driver vmwarefusion docker-vm
 		# Use the docker-vm
		eval "$(docker-machine env docker-vm)"

## How to use

Create a folder for the project and clone this repo


### To start

In the project folder run this to start the container

		docker-compose up -d

### Get ip address

		docker-machine ip docker-vm

You can also check the running machines and there ip with 

		docker-machine ls

Put the ip in a browser and see the welcome message

### To stop the containers

		docker-compose stop

### Display running containers

		docker ps

### Connect to MySQL command line

Run this to list containers
		docker ps

Copy the Mysql container ID and run ( for example ID = 5207587d116b )

		docker exec -it 5207587d116b /bin/bash

Now you can enter

		mysql -u root -p secret

### Connect with database GUI 

Connection params

		ip: ip of the docker vm
		port: 3306

### Use phpadmin

Use the url with IP address of the docker machine and port 8080

For example : http://192.168.104.150:8080/
