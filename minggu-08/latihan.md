## Try Docker Compose</br>
This tutorial is designed to introduce the key concepts of Docker Compose whilst building a simple Python web application. The application uses the Flask framework and maintains a hit counter in Redis. The concepts demonstrated here should be understandable even if you’re not familiar with Python.</br>

### Prerequisites</br>
You need to have Docker Engine and Docker Compose on your machine. You can either:</br>
1. Install Docker Engine and Docker Compose as standalone binaries</br>
2. Install Docker Desktop which includes both Docker Engine and Docker Compose</br>
You don’t need to install Python or Redis, as both are provided by Docker images.</br>
</br>

### Step 1: Define the application dependencies</br>
1. Create a directory for the project:</br>
<blockquote> mkdir composetest</br>
cd composetest</blockquote>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-08/image/latihan-01.PNG"/></br>
2. Create a file called app.py in your project directory and paste the following code in:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-08/image/latihan-02.PNG"/></br>
In this example, redis is the hostname of the redis container on the application’s network. We use the default port for Redis, 6379.</br>
3. Create another file called requirements.txt in your project directory and paste the following code in:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-08/image/latihan-03.PNG"/></br>
</br>

### Step 2: Create a Dockerfile</br>
In your project directory, create a file named Dockerfile and paste the following code in:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-08/image/latihan-04.PNG"/></br>
</br>
### Step 3: Define services in a Compose file</br>
Create a file called docker-compose.yml in your project directory and paste the following:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-08/image/latihan-05.PNG"/></br>
This Compose file defines two services: web and redis.</br>
The web service uses an image that’s built from the Dockerfile in the current directory. It then binds the container and the host machine to the exposed port, 8000. This example service uses the default port for the Flask web server, 5000.</br>
The redis service uses a public Redis image pulled from the Docker Hub registry.</br>
</br>
### Step 4: Build and run your app with Compose</br>
1. From your project directory, start up your application by running docker compose up.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-08/image/latihan-06.PNG"/></br>
Compose pulls a Redis image, builds an image for your code, and starts the services you defined. In this case, the code is statically copied into the image at build time.</br>
2. Enter http://localhost:8000/ in a browser to see the application running.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-08/image/latihan-07.PNG"/></br>
3. Switch to another terminal window, and type docker image ls to list local images.</br>
Listing images at this point should return redis and web.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-08/image/latihan-08.PNG"/></br>
</br>
### 5: Edit the Compose file to add a bind mount</br>
Edit docker-compose.yml in your project directory to add a bind mount for the web service:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-08/image/latihan-09.PNG"/></br>
</br>
### Step 6: Re-build and run the app with Compose</br>
From your project directory, type docker compose up to build the app with the updated Compose file, and run it.Check the Hello World message in a web browser again, and refresh to see the count increment.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-08/image/latihan-10.PNG"/></br>
</br>
### Step 7: Update the application</br>
1. Change the greeting in app.py and save it. For example, change the Hello World! message to Hello from Docker!:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-08/image/latihan-11.PNG"/></br>
2. Refresh the app in your browser. The greeting should be updated, and the counter should still be incrementing.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-08/image/latihan-12.PNG"/></br>
</br>
### Step 8: Experiment with some other commands</br>
1. If you want to run your services in the background, you can pass the -d flag (for “detached” mode) to docker compose up and use docker compose ps to see what is currently running:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-08/image/latihan-13.PNG"/></br>
2. The docker compose run command allows you to run one-off commands for your services. For example, to see what environment variables are available to the web service:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-08/image/latihan-14.PNG"/></br>
3. If you started Compose with docker compose up -d, stop your services once you’ve finished with them:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-08/image/latihan-15.PNG"/></br>
4. You can bring everything down, removing the containers entirely, with the down command. Pass --volumes to also remove the data volume used by the Redis container:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-08/image/latihan-16.PNG"/></br>

Source : [Getting Started - Docker Compose](https://docs.docker.com/compose/gettingstarted/)