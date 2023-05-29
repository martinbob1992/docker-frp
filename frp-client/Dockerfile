FROM alpine:3.14

MAINTAINER Martin <610385220@qq.com>
# 设置时区
RUN apk add tzdata && \
    cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    echo "Asia/Shanghai" > /etc/timezone && \
    apk del tzdata

ENV WORK_DIR="/frp"
RUN mkdir -p ${WORK_DIR}
COPY source ${WORK_DIR}
WORKDIR ${WORK_DIR}
VOLUME ${WORK_DIR}/logs
RUN chmod a+x frpc

ENTRYPOINT ./frpc -c ./config/frpc.ini
