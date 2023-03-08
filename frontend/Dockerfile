FROM node:lts as uiapp
WORKDIR /node/app
COPY ./package.json ./.
RUN npm install
COPY ./. ./.
RUN npm run build

FROM nginx
WORKDIR /usr/share/nginx/html
COPY  --from=uiapp /node/app/build ./.