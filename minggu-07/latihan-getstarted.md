### Get Started Docker</br>
#### Containerize an Application </br>
##### Get the App </br>
1. Clone the getting-started repository using the following command :</br>
<blockquote> git clone https://github.com/docker/getting-started.git </blockquote></br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-07/get-stared-01.PNG"/></br>

2. View the contents of the cloned repository. Inside the getting-started/app directory you should see package.json and two subdirectories (src and spec). </br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-07/get-stared-02.PNG"/></br>

##### Build the app’s container image </br>
1. In the app directory, the same location as the package.json file, create a file named Dockerfile. You can use the following commands below to create a Dockerfile based on your operating system. </br>
In the terminal, run the following commands listed below.

Change directory to the app directory. Replace /path/to/app with the path to your getting-started/app directory.</br>
<blockquote> cd /path/to/app </blockquote></br>

Create an empty file named Dockerfile.</br>
<blockquote> touch Dockerfile </blockquote></br>
2. Using a text editor or code editor, add the following contents to the Dockerfile:
<blockquote> # syntax=docker/dockerfile:1
   
FROM node:18-alpine
WORKDIR /app
COPY . .
RUN yarn install --production
CMD ["node", "src/index.js"]
EXPOSE 3000 </blockquote></br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-07/get-stared-03.PNG"/></br>

3. Build the container image using the following commands:</br>

In the terminal, change directory to the getting-started/app directory. Replace /path/to/app with the path to your getting-started/app directory.</br>

Build the container image.</br>
<blockquote> docker build -t getting-started . </blockquote></br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-07/get-stared-04.PNG"/></br>

##### Start an app container </br>
1. Start your container using the docker run command and specify the name of the image you just created:</br>
<blockquote>docker run -dp 3000:3000 getting-started</blockquote></br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-07/get-stared-05.PNG"/></br>

2. After a few seconds, open your web browser to http://localhost:3000. You should see your app.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-07/get-stared-06.PNG"/></br>

Run the following docker ps command in a terminal to list your containers.</br>
<blockquote>docker ps</blockquote></br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-07/get-stared-07.PNG"/></br>