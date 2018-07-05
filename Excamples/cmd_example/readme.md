# example shows how to use run command

##build
docker build -t cmd_example .

##Run
docker container run cmd_example

###change the actual command the container will run to screenfetch command
docker container run cmd_example screenfetch -E

