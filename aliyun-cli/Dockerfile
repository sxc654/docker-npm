FROM node:10-alpine

#******************更换Alpine源为mirrors.ustc.edu.cn******************
RUN echo http://mirrors.ustc.edu.cn/alpine/latest-stable/main > /etc/apk/repositories && \
    echo http://mirrors.ustc.edu.cn/alpine/latest-stable/community >> /etc/apk/repositories
    
RUN apk update \
    && apk add --no-cache git openssh-client rsync make tzdata \
    && ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && echo "Asia/Shanghai" > /etc/timezone \
    apk del --no-cache tzdata

RUN wget https://aliyuncli.alicdn.com/aliyun-cli-linux-3.0.2-amd64.tgz
RUN tar -xvzf aliyun-cli-linux-3.0.2-amd64.tgz
RUN rm aliyun-cli-linux-3.0.2-amd64.tgz
RUN cp aliyun /usr/local/bin