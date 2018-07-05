# example shows how to use run command

##build
docker build -t entrypoint_example .

##Run
docker container run entrypoint_example
docker container run entrypoint_example hellow

###the actual command can not be change it will alway be cowsay, but the parameters can be passed. this command will show cow saying screenfetch -E
docker container run entrypoint_example screenfetch -E

