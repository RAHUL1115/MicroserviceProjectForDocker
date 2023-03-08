FROM node:lts as dev
WORKDIR /node/app
COPY ./package.json ./.
RUN npm install
COPY ./. ./.

FROM node:lts-slim
WORKDIR /node/app
COPY  --from=dev /node/app/ ./.
CMD [ "npm","start" ]