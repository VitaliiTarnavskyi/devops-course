FROM node:22-alpine

WORKDIR /var/www/frontend

COPY ./frontend .

COPY ./docker/frontend/entrypoint.sh /usr/local/bin/entrypoint.sh

RUN chmod +x /usr/local/bin/entrypoint.sh

RUN npm install
RUN npm run build

CMD [ "npm" , "start" ]

