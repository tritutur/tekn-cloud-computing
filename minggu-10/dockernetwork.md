### Section #1 - Networking Basics
#### Step 1: The Docker Network Command
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/img1.png"/></br>
#### Step 2: List networks</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/img2.png"/></br>
#### Step 3: Inspect a network</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/img3.png"/></br>
#### Step 4: List network driver plugins</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/img4.png"/></br>

### Section #2 - Bridge Networking
#### Step 1: The Basics
1. Every clean installation of Docker comes with a pre-built network called bridge. Verify this with the docker network ls.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/img5.png"/></br>
2. Install the brctl command and use it to list the Linux bridges</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/img6.png"/></br>
3. Then, list the bridges on your Docker host</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/img7.png"/></br>
4. You can also use the ip a command to view details</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/img8.png"/></br>

#### Step 2: Connect a container
1. Create a new container</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/img9.png"/></br>
2. Verify our example container is up</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/img10.png"/></br>
3. Run the brctl show</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/img11.png"/></br>
4. Inspect the bridge network</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/img12.png"/></br>

#### Step 3: Test network connectivity
1. Ping the IP address of the container from the shell prompt of your Docker host</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/img13.png"/></br>
2. Run docker ps to get ID container</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/img14.png"/></br>
3. Run a shell inside that ubuntu container, by running docker exec -it CONTAINER_ID /bin/bash.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/img15.png"/></br>
4. Run apt-get update && apt-get install -y iputils-ping</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/img16.png"/></br>
5. Ping www.github.com</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/img17.png"/></br>
6. Disconnect our shell from the container</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/img18.png"/></br>
7. Stop this container so we clean things up from this test, by running docker stop CONTAINER_ID.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/img19.png"/></br>

#### Step 4: Configure NAT for external connectivity
1. Start a new container based off the official NGINX image</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/img20.png"/></br>
2. Review the container status and port mappings</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/img21.png"/></br>
3. Connect from your Docker host</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/img22.png"/></br>

### Task 3: Modify a running website
#### Step 1: The Basics
1. docker swarm init</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/docker-swarm.png"/></br>

2. docker node ls</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/docker-swarm-ls.png"/></br>

#### Step 2: Create an overlay network
1. docker network create</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/docker-network-create.png"/></br>

2. docker network inspect </br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/docker-network-inspect-overnet.png"/></br>

#### Step 3: Create a service
1. docker servie create</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/docker-service-create.png"/></br>

2. docker service my service</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/docker-service-myservice.png"/></br>

#### Step 4: Test the network
1. docker apt install and update</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/docker-cat-resolv.png"/></br>


#### Step 5: Test service discovery
1. cat resolv </br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/docker-cat-resolv.png"/></br>
### Cleaning Up</br>
1. docker ps</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-10/image/docker-ps-cleaningup.png"/></br>

