# example shows how the health check works

##build
docker build -t health .

##run container
docker container run -d --name health --cap-add NET_ADMIN -p 80:80 health

##scenario
###check container health state and you will se the health under the status column
docker container ls
 
###bring the container port 80 down so it will be unhealthy then monitor the result
docker exec -it health sh -c "sleep 10; ip link set lo down; sleep 15; ip link set lo up" &

watch -n 1 "docker container ls"


##we can see the health also by
 docker system events --since 30m --filter event=health_status