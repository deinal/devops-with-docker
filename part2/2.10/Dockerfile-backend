FROM node:10

# Create app directory
WORKDIR /usr/src/app

# Install app dependencies
COPY package*.json ./

RUN npm install

# Bundle app source
COPY . .

ENV FRONT_URL=http://localhost:5000
EXPOSE 8000
CMD npm start
