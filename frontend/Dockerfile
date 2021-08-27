FROM node:14.17.5-alpine
WORKDIR /app
COPY . .
RUN yarn install
RUN yarn build
LABEL application="cloud7"
LABEL MAINTAINER="Leo B. <bernerdoodle@outlook.de>"
ENV NUXT_HOST=0.0.0.0
ENV NUXT_PORT=5000
CMD ["yarn", "dev"]