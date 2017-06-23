FROM debian:jessie-20170620

MAINTAINER zhouyq@goodrain.com

# Timezone
RUN echo "Asia/Shanghai" > /etc/timezone;dpkg-reconfigure -f noninteractive tzdata

ADD ./sources.list  /etc/apt/sources.list

RUN echo 'APT::Install-Recommends 0;' >> /etc/apt/apt.conf.d/01norecommends \
 && echo 'APT::Install-Suggests 0;' >> /etc/apt/apt.conf.d/01norecommends \
 && apt-get update \
 && apt-get install -y vim.tiny wget sudo net-tools ca-certificates unzip apt-transport-https \
 && apt-get autoremove \
 && apt-get clean all \
 && rm -rf /var/lib/apt/lists/* \
 && rm -rf /var/cache/debconf/* \
 && rm -rf /var/lib/dpkg/info/* /usr/share/doc/* /usr/share/man/* 
