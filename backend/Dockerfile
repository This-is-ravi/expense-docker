FROM node:20.15.0-alpine3.20
EXPOSE 8080
#Backend connecting to mysql DB 
ENV DB_HOST=mysql
#add user for alpine OS, group and UN is expense
RUN addgroup -S expense && adduser -S expense -G expense \
    && mkdir /opt/server \
    && chown expense:expense -R /opt/server
WORKDIR /opt/server 
COPY package.json .
COPY *.js /opt/server/
RUN npm install
#with this normal expense user below CMD command wil run
USER expense
EXPOSE 8081
CMD [ "node","index.js" ]