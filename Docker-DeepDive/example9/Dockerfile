FROM ubuntu:17.10

RUN apt-get update && apt-get install -y iputils-ping traceroute apache2

EXPOSE 80 6000 9000 7000

ENTRYPOINT ["apache2ctl"]
CMD ["-D", "FOREGROUND"]

