
# Docker Practice: Creating and Attaching to Containers

This document captures my hands-on practice with Docker containers using the **Ubuntu** image.

 

---

 

## Steps Practiced

 

### 1. Creating a Container

I created a container from the `ubuntu` image using the following command:

docker create --name Raj09 ubuntu
image.png

✅ The container Raj09 was created successfully.

2. Starting the Container

I then started the container:

docker start Raj09
image.png

3. Attaching to the Container

Next, I tried connecting to the container using the attach command:

docker attach dd31d6088ed8
image.png

⚠️ Error received:

You cannot attach to a stopped container, start it first

4. Troubleshooting

After investigating, I realized the issue was that Ubuntu containers run in the background by default. To interact with them, I needed to use the interactive terminal mode (-it).

5. Creating a Container with -it

I created a new container with interactive terminal enabled:

docker create -it --name Raj20 ubuntu
image.png

✅ The container Raj20 was created successfully.

6. Starting and Attaching

I then started and attached to the container:

docker start Raj20

docker attach Raj20

image.png

✅ Successfully connected to the container.

Lessons Learned:
-->Without the -it option, Ubuntu containers run in the background, making it impossible to attach interactively.
-->Using -it (interactive terminal) is necessary when creating containers you want to directly interact with.
-->Always check the container status before attempting to attach.
 

