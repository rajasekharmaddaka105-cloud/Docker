# 🐳 Removing Docker Images

## Problem
I tried removing an image from the Docker host using the command:
docker rmi <Image Name>
Example:
docker rmi ubuntu
It threw the following error:
 
Error response from daemon: conflict: unable to remove repository reference "ubuntu" (must force) - container dd4e38116549 is using its referenced image 802541663949
 
Analysis
From the error, I understood that there are containers which are using this image.
So, I checked the running containers:
docker ps
 
The output showed nothing, which means no containers were running.
Then, I checked all containers (including stopped ones):
docker ps -a
 
This gave me the details of all containers such as CONTAINER ID, IMAGE, COMMAND, CREATED, STATUS, PORTS, and NAMES.
 
Solution:
I removed the containers (which were not needed) using:
docker rm <Container ID or Container Name>
Example:
docker rm 26087c2764c3
 
 
After removing the unnecessary containers, I was able to remove the image successfully.
 

⚡ Force Removing an Image
If you want to forcefully remove an image even if it is still referenced by containers, you can use:
docker rmi -f <image name>

 
⚠️ Note: This will also remove the containers associated with the image. Use with caution.

---
 Lessons Learned
•	Docker will not allow removal of an image if any container (running or stopped) is referencing it.
•	docker ps shows only running containers, while docker ps -a shows all containers.
•	Unused containers must be removed before deleting an image.
•	The error message itself gives a strong hint about what’s blocking the image removal.
•	Use docker rmi -f <image-name> only if you want to force remove the image and its dependent containers.




