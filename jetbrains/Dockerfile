FROM ubuntu:20.04
RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y git curl unzip procps time mc strace
RUN git clone https://github.com/JetBrains/intellij-samples.git /project && \
    cd /project && git reset --hard 990b89a3b43280edaf42046a6e5b4e3373d42700
WORKDIR /project
ARG IDEA_BUILD=213.4631
RUN curl -fsSL -o /ide.tar.gz https://download.jetbrains.com/idea/ideaIU-2021.3.tar.gz && \
    mkdir /ide && \
    tar xfz /ide.tar.gz --strip-components=1 -C /ide && \
    rm /ide.tar.gz
CMD /ide/bin/remote-dev-server.sh run /project --listenOn 0.0.0.0 --port 5993