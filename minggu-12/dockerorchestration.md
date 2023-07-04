### Section #1 - What is Orchestration</br>
So, what is Orchestration anyways? Well, Orchestration is probably best described using an example. Let’s say that you have an application that has high traffic along with high-availability requirements. Due to these requirements, you typically want to deploy across at least 3+ machines, so that in the event a host fails, your application will still be accessible from at least two others. Obviously, this is just an example and your use-case will likely have its own requirements, but you get the idea.</br>

### Section #2 - Configure Swarm Mode</br>
1. Running things manually and on a single host would be to create a new container on node1 by running docker run -dt ubuntu sleep infinity</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-12/image/img1.png"/></br>
2. You can verify our example container is up by running docker ps on node1.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-12/image/img2.png"/></br>

#### Step 2.1 - Create a Manager node</br>
1. Run docker swarm init on node1.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-12/image/img3.png"/></br>
2. Run the docker info command to verify that node1 was successfully configured as a swarm manager node.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-12/image/img4.png"/></br>

#### Step 2.2 - Join Worker nodes to the Swarm</br>
1. Copy and paste command from output docker swarm node1 to terminal of node2 and node3.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-12/image/img5.png"/></br>
2. Switch back to node1, and run a docker node ls to verify that both nodes are part of the Swarm</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-12/image/img6.png"/></br>


### Section #3 - Deploy applications across multiple hosts</br>
#### Step 3.1 - Deploy the application components as Docker services</br>
1. Let’s deploy sleep as a Service across our Docker Swarm.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-12/image/img7.png"/></br>
2. Verify that the service create has been received by the Swarm manager.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-12/image/img8.png"/></br>

### Section #4 - Scale the application</br>
1. Scale the number of containers in the sleep-app service to 7 with the docker service update --replicas 7 sleep-app command. replicas is the term we use to describe identical containers providing the same service.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-12/image/step4-service-update.png"/></br>
2. We are going to use the docker service ps sleep-app command. If you do this quick enough after using the --replicas option you can see the containers come up in real time.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-12/image/step4-docker-ls-sleep.png"/></br>
3. Scale the service back down to just four containers with the docker service update --replicas 4 sleep-app command</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-12/image/step4-docker-replicas-4.png"/></br>

### Section #5 - Drain a node and reschedule the containers
1. Take a look at the status of your nodes again by running docker node ls on node1.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-12/image/step5-docker-ls.png"/></br>
2. We are going to take the ID for node2 and run docker node update --availability drain yournodeid. We are using the node2 host ID as input into our drain command. Replace yournodeid with the id of node2.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-12/image/step5-docker-node-update.png"/></br>
3. Lastly, check the service again on node1 to make sure that the container were rescheduled. You should see all four containers running on the remaining two nodes.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-12/image/step5-docker-service-sleep.png"/></br>

### Cleaning Up
1. Execute the docker service rm sleep-app command on node1 to remove the service called myservice</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-12/image/cleaning-service-rm.png"/></br>
2. Execute the docker ps command on node1 to get a list of running containers</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-12/image/cleaning-docker-ps.png"/></br>
3. You can use the docker kill <CONTAINER ID> command on node1 to kill the sleep container we started at the beginning.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-12/image/cleaning-docker-kill.png"/></br>
4. Lets run docker swarm leave --force on node1.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-12/image/cleaning-docker-swarm-leave.png"/></br>