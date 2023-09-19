FROM ubuntu:23.04
ENV TZ=Europe/Moscow
ENV EULA="eula=true"

RUN apt-get update
RUN apt-get install -y nano
RUN apt-get install -y wget

RUN mkdir minecraft
WORKDIR /minecraft
RUN wget https://maven.minecraftforge.net/net/minecraftforge/forge/1.19.2-43.2.0/forge-1.19.2-43.2.0-installer.jar
RUN apt-get install -y libc6-x32 libc6-i386
RUN apt-get install -y default-jdk
RUN java -jar forge-1.19.2-43.2.0-installer.jar --installServer
RUN rm forge-1.19.2-43.2.0-installer.jar
RUN echo $EULA > eula.txt
COPY server.properties /minecraft/
ENTRYPOINT ["/minecraft/run.sh"]
