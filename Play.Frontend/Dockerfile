# syntax=docker/dockerfile:1.4

# 1. For build React app
FROM node:22-alpine 

# Set working directory
WORKDIR /app

# 
COPY public/ /app/public
COPY src/ /app/src
COPY package.json /app/
COPY package-lock.json /app/
# Same as npm install
RUN npm install

CMD ["npm","start"]
