FROM node:10.14.2-alpine AS builder
WORKDIR /app
COPY . .
RUN yarn install && yarn build

FROM node:10.14.2-alpine
COPY --from=builder ./app/dist ./dist
COPY package.json .
ENV WEB_PORT=3002
CMD [ "yarn", "start" ]

