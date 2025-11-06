### **Lab 1**

*Check Docker Download*
This step just checked if docker was properly installed and the current version its on.
![[Screenshot 2025-10-10 122041.png]]

*Pull Postgres*
This step pulled the Postgres image from Docker hub, the output visualized the download. Postgres is for relational database management.
![[Screenshot 2025-10-10 123056.png]]

*Pulling Redis*
This step was pulling Redis, which is used for in-memory data storing (caching, etc.).
![[Screenshot 2025-10-10 123258.png]]

*Visualizing Redis Container by Running Detached*
This step was rerunning Redis container detached so I could visualize it with `docker ps`
![[Screenshot 2025-10-10 123343.png]]


*Get Container ID*
Get ID's of containers by logging them and their details with the command `docker ps -a`
![[Screenshot 2025-10-10 123503.png]]

*Start Docker Container with ID*
This step was to learn the command to start a container based on ID.
![[Screenshot 2025-10-10 123448.png]]

*Stop Containers*
This step was to stop all the containers used in the lab for learning.
![[Screenshot 2025-10-10 123424.png]]




### **Lab 2**

*Pull Redis Image*
This was to pull Redis image locally.
![[Screenshot 2025-10-10 123606.png]]

*Verify Redis Image Pulled*
This was to verify Redis was pulled.
![[Screenshot 2025-10-10 124027.png]]

*Bind Ports*
Bind default 6379 port to laptop 6000 port
![[Pasted image 20251010210921.png]]

*Run Redis 7.2 with Different Port*
Runs image on different port number, outputs container ID.
![[Pasted image 20251010211030.png]]

*Give own Docker name*
Give container new name, outputs id.
![[Screenshot 2025-10-10 124123.png]]

*Debug Docker Container*
See logs for particular container using `docker logs` and a container ID
![[Pasted image 20251010211344.png]]

*Get In Interactive Terminal*
Enter interactive terminal, where you can check environment variables. 
![[Screenshot 2025-10-10 124235.png]]

### **Lab 3**

*Clone Repository*
Clone the given GitHub repository to local.
![[Pasted image 20251010141809.png]]

*Run MongoDB*
Create new MongoDB container using `docker run`, runs in detached, maps port 27017 on machine to 27017 on container, sets env variables inside container, connects container to custom docker network `mongo-network`
![[Pasted image 20251010143336.png]]

*Run MongoDB Express*
Start a new container in detached, map port 8081 to 8081, set admin username and password, attaches it to same network as `mongodb`.
![[Pasted image 20251010145912.png]]

*Run Logs for Mongo Express for Verification*
Open logs for `mongo-express` to see if server is listening
![[Pasted image 20251010145822.png]]

*Open Mongo Express on Browser*
Open `mongo-express` on browser at port 8081 to see Mongo UI.



![[Pasted image 20251010145934.png]]


*Go Into App Directory, Install npm and node*
Install npm and node by `cd` into app directory so app can run.
![[Pasted image 20251010205521.png]]

*Check if Running*
Check if app is running on port 3000 and when done, exit with `ctrl+c`
![[Pasted image 20251010205659.png]]
![[Pasted image 20251010205719.png]]

___

### **Reflection**

- The hardest part of the project was setting up Mongo Express, I kept getting name does not resolve. I ended up realizing they had to be on the same custom Docker network mongo-network and the env variables had to match exactly, no typos allowed. Through this process I learned how container networking works and how Docker containers communicate.

- I learned how Docker isolates applications, but allows them to still interact through networks. Docker creates a single portable unit called a container to fix the "it works on my computer problem", and ensures projects run consistently across different  environments.
- This is much faster and better compared to traditional VMs since they use the host's OS kernel instead of running a full guest OS. Although VMs can isolate better, they require a bunch of resources, containers can scale a lot better.