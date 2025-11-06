**Charles Liu**
Dr. Parteek Kumar
$10/15/2025$

___

### **1. Containerize an Application**

*Git Clone*
Clone the starting project from Git.
![[Pasted image 20251015122802.png]]

*View Contents*
Verify the structure
```text
├── getting-started-app/
│ ├── .dockerignore
│ ├── package.json
│ ├── README.md
│ ├── spec/
│ ├── src/
│ └── yarn.lock
```
![[Pasted image 20251015122854.png]]

*Create Dockerfile*
Create the Dockerfile, which helps sets up the images. Creates a base image with `node:lts-alpine` that comes with Node,js and Yarn pre-installed. Copies source code and installs necessary dependencies.
![[Pasted image 20251015123042.png]]

*Docker Build*
Build a new image, tags the image with `getting-started`, `.` means find Dockerfile in current directory.
![[Pasted image 20251015123504.png]]

*Start an App Container: Docker Run*
Run the container, `-d` flag means run in background with detach, `-p` publishes to port specified (`localhost:3000`)
![[Pasted image 20251015123618.png]]

*Verify App is Running*
![[Pasted image 20251015123731.png]]

*Test the App*
![[Pasted image 20251015123801.png]]

*Show Docker Containers*
List the current docker containers with `docker-ps`. The image is called `getting-started`, which is from our tag earlier.
![[Pasted image 20251015123912.png]]

___

### **2. Update the Application**

*Edit the Code*
Changed `"No items yet!"` to `"You have no todo items yet!"`
![[Pasted image 20251015124201.png]]

*Run Docker Build*
Build the container again like before.
![[Pasted image 20251015124306.png]]

*Run the Container but Fail*
Run the container, but the old one is still running and port `3000` is used, so we need to remove the old container first.
![[Pasted image 20251015124342.png]]

*List Containers to Get Old Container ID*
![[Pasted image 20251015124439.png]]

*Stop Old Container with the ID*
![[Pasted image 20251015124503.png]]

*Remove the Old Container with the ID*
![[Pasted image 20251015124531.png]]

*Run Docker Container (Successfully)*
We have removed the old container at the port we wanted, so now `docker run` will work.
![[Pasted image 20251015124631.png]]

*Verify Update*
The app did indeed update the empty display text.
![[Pasted image 20251015124704.png]]

___

### **3. Share the Application**

*Create Repository*
Create the DockerHub repository with `getting-started` as name.
![[Pasted image 20251015124823.png]]

*Notice the Push Command*
Docker provides us with a command to push the new tag to the DockerHub repo.
![[Pasted image 20251015124952.png]]

*Docker Push (but Fail)*
Image isn't tag correctly yet, Docker is looking for image with name `docker/getting started` but local image is called `getting started`
![[Pasted image 20251015125030.png]]

*Verify the above*
![[Pasted image 20251015125133.png]]

*Give image new name*
![[Pasted image 20251015125515.png]]

*Run Docker Push (Successfully)*
![[Pasted image 20251015125602.png]]

___

### **4. Persist the Database**

*Start an Alpine Container, Create New File*
Puts file called `greeting.txt` in the new Alpine container.
![[Pasted image 20251022134320.png]]

*Check if File Exists*
Check if file exists with `stat` command, it doesn't, as the top writeable layer of each container is isolated.
![[Pasted image 20251022134441.png]]

*Create a Volume*
Create a volume, also remove todo app container (removed already, but not pictured in screenshot as was removed a while before realizing screenshot was necessary). Instead, `docker ps` shows its not up.

![[Pasted image 20251022134716.png]]

*Start Todo App Container*
Start container, but we add the `--mount` to specify a volume mount. We also give the volume a name and mount it to `/etc/todos`.
![[Pasted image 20251022134819.png]]

*Add Items to Todo App*
Add items to todo app, so we can verify data persists.
![[Pasted image 20251022135008.png]]


*Stop Container*
Stop container by getting id and removing
![[Pasted image 20251022135217.png]]

*Start a New Container*
Follow the previous steps again to start up the container
![[Pasted image 20251022135424.png]]

*Open the App, Check Data*
Items are still there, data persisted
![[Pasted image 20251022135439.png]]

*Remove Container Again*
![[Pasted image 20251022135509.png]]

*See Where Docker Is Storing Your Data*
When you use a volume, you can see where Docker stores your data using `docker volume inspect`, where `Mountpoint` is the actual location of the data on the disk.
![[Pasted image 20251022135547.png]]
___

### **5. Use Bind Mounts**

*Apply File Sharing*
![[Pasted image 20251022140248.png]]

*Start Bash in Ubuntu Container with Bind Mount*
![[Pasted image 20251022150846.png]]

*Check Directories*
![[Pasted image 20251022150930.png]]

*Change Directory to the `src` Directory*

![[Pasted image 20251022151015.png]]

*Create New File Called `myfile.txt`*
![[Pasted image 20251022151106.png]]

*Delete `myfile.txt` From Host*
![[Pasted image 20251022151250.png]]

*File Deleted*
In container, running `ls` verifies the file was deleted.
![[Pasted image 20251022161908.png]]

*Exit*
Exit with `Ctrl`+`D`
![[Pasted image 20251022161937.png]]

*Verify Nothing Running*
![[Pasted image 20251022162114.png]]

*Run Container*
Run in detached, sets the working directory, binds the mount, installs packages
![[Pasted image 20251022162158.png]]

*Watch Logs*
Watch logs with `docker logs -f <container-id>`

![[Pasted image 20251022162531.png]]

*Changed to Add*
Changed "Add Item" to "Add" on button
![[Pasted image 20251022162639.png]]

*Refresh Browser*
It was reflected almost instantly since we had a bind mount.
![[Pasted image 20251022162739.png]]

*Stop Container and Build New Image*
![[Pasted image 20251022162828.png]]

___

### **6. Multi-Container Apps**

*Create the Network*
![[Pasted image 20251022162947.png]]

*Start a MySQL Container and Attach it to the Network*
![[Pasted image 20251022163132.png]]

*Connect Database to Verify*
Verify the database connects
![[Pasted image 20251022163255.png]]
![[Pasted image 20251022163326.png]]

*Exit MySQL shell, return to machine shell*

![[Pasted image 20251022163349.png]]

*Start a new container using Nicolaka/Netshoot image*
![[Pasted image 20251022163548.png]]

*Use `dig`*
Dig is a usefl DNS tool to look up the IP address for the hostname `mysql`. In the "ANSWER SECTION" there is an `A` record that is the IP address value.
![[Pasted image 20251022163633.png]]

*Run Container, Specify Env Variables*
Run the container  but make sure to specify the env variables like `MYSQL_HOST`, `MYSQL_USER`, etc.
![[Pasted image 20251022163927.png]]

*Look at Logs*
Look at logs, and verify its using mysql database
![[Pasted image 20251022164008.png]]

*Add Items*
![[Pasted image 20251022164050.png]]

*Prove Items are Written to Database*
![[Pasted image 20251022164204.png]]

___

### **7. Use Docker Compose**

*Set up Compose Yaml*
Set up compose yaml, which allows standardized actions like naming, downloading apps, setting directories and env variables, etc.
![[Pasted image 20251022164329.png]]

*Define MySQL service*
Define mysql service and make sure it gets the network alias, has volume mapping, and has env variables set.
![[Pasted image 20251022164601.png]]

*Start up Application Stack*
Created volume as well as network. `docker compose` by default creates a network for application stack specifically.
![[Pasted image 20251022164702.png]]

*See Logs*
Great for timing related issues, `-f` flag follows the log for live output.
![[Pasted image 20251022164929.png]]

*Verify it's running*
![[Pasted image 20251022164944.png]]

*See App Stack in Docker Desktop Dashboard*
Names are more specific, since we defined them in `compose.yaml`
![[Pasted image 20251022165053.png]]

*Tear it Down*
![[Pasted image 20251022165128.png]]

___

### **8. Image-Building Best Practices**

*See Docker Image History*
See layers in the getting-started image I created, where each line is a layer, and its newest first.
![[Pasted image 20251022165215.png]]

*No Truncate*
Several lines are truncated, if you don't want that you can do `--no-trunc` flag, (this went way off screen for my terminal)
![[Pasted image 20251022165322.png]]

*Update Dockerfile to copy `package.json` first*
We update the Dockerfile to update `package.json` first, install dependencies, then copy everything else.
![[Pasted image 20251022165436.png]]

*Build a new image*
![[Pasted image 20251022165518.png]]

*Make Change to `index.html`*
Made change to `src/static/index.html`
![[Pasted image 20251022165621.png]]

*Build image again*
Build again, but output looks a little different. It was much faster, as some steps are cached.
![[Pasted image 20251022165647.png]]

___

### **Reflection**

This Docker workshop taught me the fundamentals of how containerization in Docker words, and how it streamlines modern software development. I learned how to build and run containers, manage multi-container apps, persist data using volumes, bind mounts, build images, layer, and more. Each part of the workshop and abilities that I previously mentioned showed how Docker containers can create environments that allow for consistent developing testing, and production. Together, they help prevent the "works on my machine" problem. Docker Compose helped me understand how to easily manage interconnected services through a single configuration file. I can see how Docker helps support scalability, automation, and more now. Containerizing applications allows isolating dependencies and faster, more predictable performance and delivery. 

Docker relates with the software engineering lifecycle since Docker images guarantee applications run identical across different machines and platforms, and also helps with testing since it allows rapid setup of reproducible test environments.

A real world scenario is an e-commerce platform which uses separate containers for frontend, backend API, and database. Docker allows each to be deployed independently and updated without downtime, and can scale horizontally for high traffic.