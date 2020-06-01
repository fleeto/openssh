FROM alpine:3.12
RUN apk add openssh-server tini -u && \
  ssh-keygen -t rsa -P "" -f /etc/ssh/ssh_host_rsa_key && \
  sed -i "s/#PermitRootLogin.*/PermitRootLogin yes/g" /etc/ssh/sshd_config && \
  echo root:Welcome2Earth | chpasswd
CMD ["tini", "/usr/sbin/sshd", "-D"]
