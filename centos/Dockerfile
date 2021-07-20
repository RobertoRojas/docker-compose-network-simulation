FROM centos:8

ARG REMOTE_USER=duser

ARG REMOTE_USER_PASSWORD=DefPass123

RUN yum update -y

RUN yum install -y openssh-server

RUN adduser $REMOTE_USER

RUN echo "$REMOTE_USER:$REMOTE_USER_PASSWORD" | chpasswd

RUN echo usermod –aG wheel "$REMOTE_USER"

RUN usermod -aG wheel $REMOTE_USER

RUN ssh-keygen -A

RUN rm -rf /run/nologin

EXPOSE 22

CMD ["/usr/sbin/sshd","-D"]
