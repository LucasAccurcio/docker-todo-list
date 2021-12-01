FROM mjgargani/puppeteer:trybe1.0
WORKDIR /docker/todo-app/tests
ADD node_modules.tar.gz ./
COPY package*.json ./
RUN npm install
COPY . ./
CMD ["npm", "test"]
