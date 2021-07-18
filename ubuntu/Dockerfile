FROM ubuntu:21.10

ARG REMOTE_USER=duser

ARG REMOTE_USER_PASSWORD=DefPass123

RUN apt-get update -y && apt-get install openssh-server sudo -y

RUN echo ${REMOTE_USER}

RUN useradd -rm -d /home/ubuntu -s /bin/bash -g root -G sudo -u 1000 ${REMOTE_USER}

RUN  echo "${REMOTE_USER}:${REMOTE_USER_PASSWORD}" | chpasswd

RUN service ssh start

EXPOSE 22

CMD ["/usr/sbin/sshd","-D"]
