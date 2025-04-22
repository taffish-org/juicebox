FROM ghcr.io/taffish-org/debian:12

LABEL maintainer="taffish@163.com"

WORKDIR /root

ENV USER=root

RUN apt-get update && \
    apt-get install -y curl git default-jdk python3-dev python3-websockify \
                       xfce4 tightvncserver xfce4-terminal xvfb x11vnc dbus-x11 && \
    cd / && \
    curl -LO https://github.com/aidenlab/JuiceboxGUI/releases/download/v3.1.4/juicebox.jar && \
    cd / && git clone https://github.com/novnc/noVNC.git && \
    echo '#!/bin/sh' > /usr/local/bin/juicebox && \
    echo 'java -Xmx4g -jar /juicebox.jar $@' >> /usr/local/bin/juicebox && \
    chmod +x /usr/local/bin/juicebox && \
    echo 'cd /' >> /root/.bashrc && \
    echo 'echo ""' >> /root/.bashrc && \
    echo 'echo "Welcome to taffish-juicebox-GUI!"' >> /root/.bashrc && \
    echo 'echo ""' >> /root/.bashrc && \
    echo 'echo "If you want to use juicebox, you can run one of the cmds:"' >> /root/.bashrc && \
    echo 'echo "  % juicebox"' >> /root/.bashrc && \
    echo 'echo "  % java -Xmx4g -jar /juicebox.jar"' >> /root/.bashrc && \
    echo 'echo "* Note: you can change {4g} to the memory you want to use."' >> /root/.bashrc && \
    echo 'echo ""' >> /root/.bashrc

ENV TAFFISH_ENV=TAFFISH
ENV TAFFISH_NAME=juicebox
