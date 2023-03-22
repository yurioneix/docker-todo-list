FROM node:14
EXPOSE 3000
WORKDIR /app
ADD ./node_modules.tar.gz /app/
COPY . /app/
ENTRYPOINT [ "npm" ]
CMD [ "start" ]