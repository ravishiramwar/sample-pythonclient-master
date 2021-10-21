FROM node:14 as builder
WORKDIR /home/user114/sample-react-master
COPY package.json ./
RUN npm install
COPY . ./
RUN npm run build
#
FROM nginx:1.19.0
WORKDIR /usr/share/nginx/html
RUN rm -rf ./*
COPY --from=builder /home/user114/sample-react-master/build .
ENTRYPOINT ["nginx", "-g", "daemon off;"]

#RUN ng build
#FROM nginx
#COPY --from=builder /app/build .