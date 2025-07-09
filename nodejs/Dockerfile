# Build Stage
FROM node:hydrogen-alpine3.21 AS builder
WORKDIR /app
# caching
COPY package.json package-lock.json index.html ./
RUN npm install
COPY . .

# Production Stage
FROM node:hydrogen-alpine3.21
WORKDIR /app
COPY --from=builder /app ./
EXPOSE 30000
CMD [ "node", "app.js" ]
