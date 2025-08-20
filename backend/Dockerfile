# Stage 1: build
FROM node:18-alpine as build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .

# Stage 2: run
FROM node:18-alpine
WORKDIR /app
COPY --from=build /app /app
EXPOSE 5000
CMD ["node", "index.js"]
