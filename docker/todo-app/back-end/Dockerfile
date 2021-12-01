FROM node:14-alpine
WORKDIR /docker/todo-app/front-end
ADD node_modules.tar.gz ./
COPY package*.json ./
COPY . ./
EXPOSE 3001
CMD ["npm", "start"]
