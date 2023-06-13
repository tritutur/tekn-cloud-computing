### Task 1: Run some simple Docker containers
#### Run a single task in an Alpine Linux container
1. Run the following command in your Linux console.
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/img1.png"/></br>
2. Docker keeps a container running as long as the process it started inside the container is still running. In this case the hostname process exits as soon as the output is written. This means the container stops. However, Docker doesn’t delete resources by default, so the container still exists in the Exited state.
List all containers.
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/img2.png"/></br>

#### Run an interactive Ubuntu container
1. Run a Docker container and access its shell.
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/img3.png"/></br>
2. Run the following commands in the container.
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/img4.png"/></br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/img5.png"/></br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/img6.png"/></br>
3. Type exit to leave the shell session. This will terminate the bash process, causing the container to exit.
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/img7.png"/></br>
4. For fun, let’s check the version of our host VM.
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/img8.png"/></br>

#### Run a background MySQL container
1. Run a new MySQL container with the following command.
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/img9.png"/></br>
2. List the running containers.
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/img10.png"/></br>
3. You can check what’s happening in your containers by using a couple of built-in Docker commands: docker container logs and docker container top.
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/img11.png"/></br>
Let’s look at the processes running inside the container.
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/img12.png"/></br>
4. List the MySQL version using docker container exec.
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/img13.png"/></br>
5. You can also use docker container exec to connect to a new shell process inside an already-running container. Executing the command below will give you an interactive shell (sh) inside your MySQL container.
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/img14.png"/></br>
6. Let’s check the version number by running the same command again, only this time from within the new shell session in the container.
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/img15.png"/></br>
7. Type exit to leave the interactive shell session.
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/img16.png"/></br>

### Task 2: Package and run a custom app using Docker
#### Build a simple website image
1. Make sure you’re in the linux_tweet_app directory.
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/img17.png"/></br>
2. Display the contents of the Dockerfile.
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/img18.png"/></br>
3. Echo the value of the variable back to the terminal to ensure it was stored correctly
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/img19.png"/></br>
4. Use the docker image build command to create a new Docker image using the instructions in the Dockerfile.
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/img20.png"/></br>
5. Use the docker container run command to start a new container from the image you created.
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/img21.png"/></br>
7. result
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/hasil.png"/></br>
6. Once you’ve accessed your website, shut it down and remove it.
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/img22.png"/></br>

### Task 3: Modify a running website
1. Let’s start the web app and mount the current directory into the container.

<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/task3-1.png"/></br>

2. Go to the running website and refresh the page. Notice that the site has changed.

<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/task3-2.png"/></br>

3. Copy a new index.html into the container.

<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/task3-3.png"/></br>

4. website

<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/task3-4.png"/></br>

5. stop and rerun without bind

<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/task3-5.png"/></br>

6. build new image

<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/task3-6.png"/></br>

7. docker image ls

<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/task3-1.png"/></br>

8. rerun new container

<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/task3-9.png"/></br>

9. running 2 container

<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/task3-19.png"/></br>

10. website

<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-09/image/task3-12.png"/></br>





