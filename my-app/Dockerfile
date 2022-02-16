FROM node:12.18.2 as build-stage

# set working directory
RUN mkdir /REACT
#copy all files from current directory to docker
COPY . /REACT

WORKDIR /REACT

# add `/usr/src/app/node_modules/.bin` to $PATH
# ENV PATH /usr/src/app/node_modules/.bin:$PATH
ENV PATH="./node_modules/.bin:$PATH"

RUN npm run build

# Stage 2
# Copy the react app build above in nginx
FROM nginx:alpine

# Set working directory to nginx asset directory
WORKDIR /usr/share/nginx/html

# Remove default nginx static assets
RUN rm -rf ./*

# Copy static assets from builder stage
COPY --from=build-stage /REACT/build .

# Containers run nginx with global directives and daemon off
ENTRYPOINT ["nginx", "-g", "daemon off;"]