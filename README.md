# TO DO LIST - FLASK - DOCKER
<b>Simple web-project to practice docker concepts </b>
- writing docker files
- building images
- running container and manage them
- playing around with docker volumes and volume mapping

## Running 

### USING DOCKER - PULLING FROM DOCKER HUB

```bash
# pull the image from docker hub
docker pull a7medayman6/todolist-flask
# create docker volume for the database to keep your tasks everytime you run ir
docker volume create todolist.db
# run the container
# map port 5000 in the container to 5001 (or any other free port)
# map the docker volume you created to /app/db 
docker run -d -p 5001:5000 -v todolist.db:/app/db todolist-flask

# open the browser, go to http://0.0.0.0:5001 and here is your todo list up and running
```

### USING DOCKER - BUILD DOCKER IMAGE

```bash
# clone the repo into your local host
git clone 

cd todo-flask

# this will build the docker image from the docker file
docker build -t todolist-flask:latest .

# check the build was succesfull
docker images | grep todolist-flask
# the output should be
# todolist-flask

# create docker volume for the database to keep your tasks everytime you run ir
docker volume create todolist.db
# run the container
# map port 5000 in the container to 5001 (or any other free port)
# map the docker volume you created to /app/db 
docker run -d -p 5001:5000 -v todolist.db:/app/db todolist-flask

# open the browser, go to http://0.0.0.0:5001 and here is your todo list up and running
```
### BUILDING

```bash
git clone
cd todo-flask
python3 -r requirements.txt
source env/bin/activate
python3 app.py
```