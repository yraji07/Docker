### this is done in both ubuntu and dockerhub server

FROM node:16-alpine3.16
RUN apk add --update npm && \
    apk add git && \
    git clone https://github.com/expressjs/express.git && \
    cd express && \
    npm install express && \
    npm install -g express-generator@4 && \
    express /tmp/foo && \
    cd /tmp/foo && \
    npm install
EXPOSE 3000
WORKDIR /tmp/foo
CMD ["npm","start"]  