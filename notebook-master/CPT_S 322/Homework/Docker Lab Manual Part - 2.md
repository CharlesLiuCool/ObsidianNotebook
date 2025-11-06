**Charles Liu**
Dr. Parteek Kumar
10/12/2025

___

### **Lab 4**

*Edit mongo.yaml*
Change mongo.yaml to perform the operations for us (easier than what we did previous lab)
![[Pasted image 20251012141957.png]]

*Run up command*
Build, create containers according to yaml.
![[Pasted image 20251012141917.png]]

*Verify Postgres is up*
![[Pasted image 20251012142033.png]]

*Install necessary packages*
![[Pasted image 20251012142113.png]]

*Verify the website is up*
![[Pasted image 20251012142132.png]]

*Check network is up*
Verify the network is up, should display "app_default"
![[Pasted image 20251012143723.png]]

*Remove network*
Turn off the containers and network, should display "removed"
![[Pasted image 20251012142413.png]]

*Check network is down*
Verify the network is up, shouldn't display "app_default"
![[Pasted image 20251012142517.png]]

___

### **Lab 5**

*Verify Dockerfile*
Check if the dockerfile looks right
- We start from base image, and set up nodejs and alpine linux.
- Specify environment variables
- Create a directory in the container
- Copy the app contents into the container from the machine
- Set default directory
- Install npm

![[Pasted image 20251012144546.png]]

*Build Docker Image*
Build the docker image from the application
Create image of name `my-app:1.0`
![[Pasted image 20251012144650.png]]

*Verify Docker Images*
Check if the images are there (my-app)
![[Pasted image 20251012144720.png]]

___

### **Lab 6**

*Docker Login*
Login to docker from command prompt
![[Pasted image 20251012144959.png]]

*Tag the Docker Image*
Tag the docker image
![[Pasted image 20251012145252.png]]

*Push the Docker image*
So others can use it
![[Pasted image 20251012145441.png]]

*Check image is in Dockerhub*

![[Pasted image 20251012145523.png]]

___

### **Extra Credit**

*Create simple program*
![[Pasted image 20251012150637.png]]

*Dockerfile Creation*
![[Pasted image 20251012150611.png]]

*Build*
![[Pasted image 20251012150653.png]]

*Push*
![[Pasted image 20251012150759.png]]

*Verify on DockerHub*
![[Pasted image 20251012150949.png]]

___