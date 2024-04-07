FROM node:14 AS build
WORKDIR /usr/src/app

COPY package*.json ./

# Install dependencies
RUN npm install
COPY . .


FROM node:14-alpine
WORKDIR /usr/src/app

COPY --from=build /usr/src/app/package.json ./
COPY --from=build /usr/src/app/node_modules ./node_modules
COPY --from=build /usr/src/app/main.js ./

EXPOSE 3000
CMD ["node", "main.js"]
