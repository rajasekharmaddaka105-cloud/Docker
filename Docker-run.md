
# Docker Practice: Understanding Container States and Run Options

This document captures my hands-on practice with **Docker containers** using `ubuntu` and `httpd` images.

---

## 1. Running an Ubuntu Container Without `-it`

docker run --name Rajdocker01 ubuntu
image.png

The container was created successfully.
But when I checked the status, it showed Exited.
This happens because the default command in ubuntu is to run and exit immediately (it doesn’t keep running in the background by itself).
2. Running an Ubuntu Container With -it

docker run -it --name Rajdocker02 ubuntu
image.png

The container was created, and I was automatically logged in (interactive terminal session).
After I typed exit, the container stopped and its status became Exited again.
3. Keeping Ubuntu Container Running With -d

docker run -d -it --name Rajdocker03 ubuntu
image.png

Adding the -d flag runs the container in detached mode.
This means the container keeps running in the background even after we exit from the interactive shell.
✅ Key Points:

-d → Detached mode (runs in the background).
-it → Interactive + TTY (brings container process to the foreground for interaction).
-d -it → Combination of both: container runs in background but you can still attach/exec into it when needed.
4. Running an HTTPD Container

docker run -d --name Rajdocker05 httpd
A black screen with white text

AI-generated content may be incorrect.

The container was created successfully and its status showed as Up.
Unlike ubuntu, the httpd container stays running because the httpd server process runs in the foreground inside the container.
Lessons Learned

Containers stop if their main process finishes or exits.
Use -it to interact with containers, and -d to keep them running in the background.
Application images like httpd, nginx, mysql stay Up because they run a server process in the foreground.
Base images like ubuntu, alpine need commands or -it sessions to stay active.
 

