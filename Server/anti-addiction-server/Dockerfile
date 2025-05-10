FROM alibaba-cloud-linux-3-registry.cn-hangzhou.cr.aliyuncs.com/alinux3/node:20.16
#设置时区
ENV TIME_ZONE=Asia/Shanghai
RUN \
  mkdir -p /usr/src/app \
#  && apk add --no-cache tzdata \
  && echo "${TIME_ZONE}" > /etc/timezone \
  && ln -sf /usr/share/zoneinfo/${TIME_ZONE} /etc/localtime

WORKDIR /usr/src/app
COPY package.json /usr/src/app/package.json
RUN npm i
COPY . /usr/src/app
EXPOSE 7001

CMD npm run docker-start
