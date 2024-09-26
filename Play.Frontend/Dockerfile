# FROM node:22-alpine

# WORKDIR /app

# COPY ["Play.Frontend/package.json", "/app/"]
# COPY ["Play.Frontend/package-lock.json", "/app/"]
# COPY ["Play.Frontend/", "/app/"]

# RUN npm install

# EXPOSE 3000

# CMD ["npm", "start"]


# FROM node:22-alpine as build-stage

# WORKDIR /app
# COPY ["Play.Frontend/package.json", "/app/"]
# COPY ["Play.Frontend/package-lock.json", "/app/"]
# COPY ["Play.Frontend/", "/app/"]

# RUN npm install
# COPY . /app
# CMD [ "npm", "start" ]

# FROM build-stage AS build
# RUN npm run build

# FROM nginx:1.19.0
# WORKDIR /usr/share/nginx/html
# RUN rm -rf ./*
# COPY --from=build /app/build .
# ENTRYPOINT ["nginx", "-g", "daemon off;"]


FROM node:alpine
WORKDIR /app
COPY ["Play.Frontend/package.json", "/app/"]
COPY ["Play.Frontend/package-lock.json", "/app/"]
RUN npm install
COPY ["Play.Frontend/", "/app/"]
RUN npm run build
EXPOSE 3000
CMD ["npm", "start"]