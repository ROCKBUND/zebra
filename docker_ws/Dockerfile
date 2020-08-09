# 基础镜像
FROM phusion/baseimage:18.04-1.0.0
# 软件源加速
# COPY sources.list /etc/apt/sources.list
RUN apt update
RUN apt-get install wget curl -y

# 安装v2ray
ARG panelurl
ARG panelkey
ARG nodeid
ARG downwithpanel
ARG speedtestrate
ARG paneltype
ARG usemysql
ARG LDNS

RUN wget -N --no-check-certificate https://raw.githubusercontent.com/CodeSheng/zebra/master/install-release.sh &&chmod +x install-release.sh
RUN bash install-release.sh --panelurl ${panelurl} --panelkey ${panelkey} --nodeid ${nodeid} --downwithpanel ${downwithpanel} --speedtestrate ${speedtestrate} --paneltype ${paneltype} --usemysql ${usemysql} --LDNS ${LDNS}

COPY ./start.sh /
RUN chmod 755 /start.sh
CMD /start.sh
