FROM strapi/base
WORKDIR /app
RUN yarn global add strapi
ENV DATABASE_CLIENT "mongo"

RUN  strapi new . \
    --dbclient=$DATABASE_CLIENT \
    --dbhost=$DATABASE_HOST \
    --dbport=$DATABASE_PORT \
    --dbname=$DATABASE_NAME \
    --dbusername=$DATABASE_USERNAME \
    --dbpassword=$DATABASE_PASSWORD \
    --dbssl=$DATABASE_SSL \  
    --no-run

RUN yarn add strapi-provider-upload-azure-storage

RUN yarn build  

ENV NODE_ENV production

EXPOSE 1337  

CMD ["yarn", "start"]
