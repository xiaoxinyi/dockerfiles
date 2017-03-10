FROM zl/caffe-torch:2.9.b

ENV DEBIAN_FRONTEND noninteractive
ENV USER root

ADD resolv.conf /etc/resolv.conf
ADD sources.list /etc/apt/sources.list

RUN apt-get update && \
    apt-get install -y --no-install-recommends ubuntu-desktop && \
    apt-get install -y gnome-panel gnome-settings-daemon metacity nautilus gnome-terminal && \
    apt-get install -y tightvncserver && \
    mkdir /root/.vnc

ADD xstartup /root/.vnc/xstartup
ADD passwd /root/.vnc/passwd

RUN chmod 600 /root/.vnc/passwd

CMD /usr/bin/vncserver :1 -geometry 1280x768 -depth 24 && tail -f /root/.vnc/*:1.log

EXPOSE 5901
EXPOSE 8888
EXPOSE 6006
EXPOSE 22