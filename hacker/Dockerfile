FROM dorowu/ubuntu-desktop-lxde-vnc:bionic

# File Creator
MAINTAINER Noah Oller Smith <nosolls@protonmail.com>

USER root

# Updates and installs needed packages for user
RUN apt update && \
	apt install -y \
	gcc \
	&& apt clean

# Creates user for env
RUN useradd -d /home/hacker -m -s /bin/bash hacker

RUN echo 'hacker:hacker' | chpasswd

ENV USER=hacker \
PASSWORD=hacker

# Allows user to run certain commands under sudo
ADD hackersudo /etc/sudoers.d/
RUN chmod 0400 /etc/sudoers.d/hackersudo

# Copies files to directory
COPY --chown=1000:100 vul_prog.c /home/hacker
COPY --chown=1000:100 write_string.c /home/hacker
