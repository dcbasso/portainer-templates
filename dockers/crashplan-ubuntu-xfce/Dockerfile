
FROM lscr.io/linuxserver/webtop:ubuntu-xfce

WORKDIR /crashplan
ADD https://download.crashplan.com/installs/agent/latest-smb-linux.tgz /crashplan
RUN apt-get update && apt-get install -y \
    cpio \
    libnss3 && \
    tar -xvf latest-smb-linux.tgz && \
    cd crashplan-install/ && \
    sudo ./install.sh -q

ENV CRASHPLAN_SRV_MAX_MEM=1024M

# Define mountable directories.
VOLUME ["/storage"]