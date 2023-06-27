### Stage Setup
1. Let’s get started by first cloning the demo code repository, changing the working directory, and checking the demo branch out.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/img1.png"/></br>

### Step 0: Basic Link Extractor Script
1. Checkout the step0 branch and list files in it.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/img2.png"/></br>
2. The linkextractor.py file is the interesting one here, so let’s look at its contents:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/img3.png"/></br>
3. However, this seemingly simple script might not be the easiest one to run on a machine that does not meet its requirements. The README.md file suggests how to run it, so let’s give it a try:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/img4.png"/></br>
4. When we tried to execute it as a script, we got the Permission denied error. Let’s check the current permissions on this file:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/img5.png"/></br>
5. We can either change it by running chmod a+x linkextractor.py or run it as a Python program instead of a self-executing script as illustrated below:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/img6.png"/></br>

### Step 1: Containerized Link Extractor Script
1. Checkout the step1 branch and list files in it.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/img7.png"/></br>
2. We have added one new file (i.e., Dockerfile) in this step. Let’s look into its contents:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/img8.png"/></br>
3. So far, we have just described how we want our Docker image to be like, but didn’t really build one. So let’s do just that:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/img9.png"/></br>
4. We have created a Docker image named linkextractor:step1 based on the Dockerfile illustrated above. If the build was successful, we should be able to see it in the list of image:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/img10.png"/></br>
5. Now, let’s run a one-off container with this image and extract links from some live web pages:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/img11.png"/></br>
6. Let’s try it on a web page with more links in it:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/img12.png"/></br>

### Step 2: Link Extractor Module with Full URI and Anchor Text
1. Checkout the step2 branch and list files in it.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/img13.png"/></br>
2. Let’s have a look at the updated script:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/img14.png"/></br>
3. Now, let’s build a new image and see these changes in effect:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/img15.png"/></br>
4. We have used a new tag linkextractor:step2 for this image so that we don’t overwrite the image from the step1 to illustrate that they can co-exist and containers can be run using either of these images.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/img16.png"/></br>
5. Running a one-off container using the linkextractor:step2 image should now yield an improved output:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/img17.png"/></br>
6. Running a container using the previous image linkextractor:step1 should still result in the old output:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/img18.png"/></br>

### Step 3: Link Extractor API Service
1. Checkout the step3 branch and list files in it.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/img19.png"/></br>
2. Let’s first look at the Dockerfile for changes:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/img20.png"/></br>
3. The linkextractor.py module remains unchanged in this step, so let’s look into the newly added main.py file:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/img21.png"/></br>
4. It’s time to build a new image with these changes in place:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/img22.png"/></br>
5. We are also assigning a name (--name=linkextractor) to the container to make it easier to see logs and kill or remove the container.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/img23.png"/></br>
6. If things go well, we should be able to see the container being listed in Up condition:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/img24.png"/></br>
7. We can now make an HTTP request in the form /api/<url> to talk to this server and fetch the response containing extracted links:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/img25.png"/></br>
8. Since the container is running in detached mode, so we can’t see what’s happening inside, but we can see logs using the name linkextractor we assigned to our container:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/img26.png"/></br>
9. We can see the messages logged when the server came up, and an entry of the request log when we ran the curl command. Now we can kill and remove this container:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/img27.png"/></br>

### Step 4: Link Extractor API and Web Front End Services
1. Checkout the step4 branch and list files in it.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/step4-checkout.png"/></br>
2. So let’s look at the docker-compose.yml file we have:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/step4-composeyml.png"/></br>
3. Now, let’s have a look at the user-facing www/index.php file:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/step4-cat_index.png"/></br>
4.Let’s bring these services up in detached mode using docker-compose utility:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/step4-compose-build.png"/></br>
5. We should now be able to talk to the API service as before:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/step4-curl-link.png"/></br>
6. Before we move on to the next step we need to shut these services down, but Docker Compose can help us take care of it very easily:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/step4-docker-down.png"/></br>

### Step 5: Redis Service for Caching
1. Checkout the step5 branch and list files in it.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/step5-checkout.png"/></br>
2. Let’s first inspect the newly added Dockerfile under the ./www folder:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/step5-cat-dockerfle.png"/></br>
3. Next, we will look at the API server’s api/main.py file where we are utilizing the Redis cache:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/step5-cat-mainpy.png"/></br>
4. Now, let’s look into the updated docker-compose.yml file:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/step5-cat-composeyml.png"/></br>
5. Let’s boot these services up:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/step5-compose-up.png"/></br>
6.  we can use docker-compose exec followed by the redis service name and the Redis CLI’s monitor command:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/step5-docker-exec-redis.png"/></br>
7. Now, shut these services down and get ready for the next step:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/step5-compose-down.png"/></br>

### Step 6: Swap Python API Service with Ruby
1. Checkout the step6 branch and list files in it.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/step6-checkout.png"/></br>
2. With these in place, let’s boot our service stack:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/step6-compose-up.png"/></br>
3. We should now be able to access the API (using the updated port number):</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/step6-curl-link.png"/></br>
4. We can use the tail command with the -f or --follow option to follow the log output live.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/step6-cat-log.png"/></br>
5. Since we have persisted logs, they should still be available after the services are gone:</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-11/image/step6-linkextractor.png"/></br>
