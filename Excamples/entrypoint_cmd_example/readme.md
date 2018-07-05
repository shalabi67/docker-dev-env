# example shows how to use run command

##build
docker build -t entry_cmd .

##Run
###show penguin saying message
docker container run entry_cmd
###show cow saying hello since the hellow argument will override the CMD arguments.
docker container run entry_cmd hellow


