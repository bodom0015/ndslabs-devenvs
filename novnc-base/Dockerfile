FROM ubuntu:xenial

RUN apt-get -qq update && \
    apt-get -qq install \
	curl \
	git \
	net-tools \
	python \
	python-numpy \
	python-pkg-resources \
	vim \
	websockify \
	wget \
	xdotool \
	xfonts-base \
	x11-utils \
	x11vnc \
	xvfb && \
    apt-get -qq clean all && \
    apt-get -qq autoclean && \
    apt-get -qq autoremove && \
    rm -rf /var/lib/apt/lists/* /tmp/*

WORKDIR /
RUN git clone --depth=1 git://github.com/kanaka/noVNC && \
    rm -rf ./noVNC/.git 

ADD index.html /noVNC/
ADD init.sh /init.sh

EXPOSE 80
ENV DISPLAY=:0
CMD ["/init.sh"]

