FROM node:10-alpine as build-stage
WORKDIR /usr/src/app
COPY . .
RUN npm install --production && mkdir dist
ENV API_URL=http://localhost:8000
CMD ["npm", "run", "build"]
RUN ls

FROM node:10-alpine
WORKDIR /bareapp
RUN npm install -g serve
COPY --from=build-stage /usr/src/app/dist .
ENV API_URL=http://localhost:8000
EXPOSE 5000
CMD ["serve", "-s", "-l", "5000", "dist"]
