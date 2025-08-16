FROM node:18-alpine AS dependencies
WORKDIR /app
COPY package*.json ./
RUN npm install --production

FROM node:18-alpine
WORKDIR /app 
COPY --from=dependencies /app/node_modules ./node_modules
COPY . .
EXPOSE 5001
CMD ["node", "src/server.js"]