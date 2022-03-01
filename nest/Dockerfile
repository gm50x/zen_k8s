FROM node:16.13-alpine3.14 AS builder
ARG target
WORKDIR /app
COPY package*.json .
RUN npm ci
COPY . .
RUN npm run build ${target}

FROM node:16.13-alpine3.14 AS runtime
ARG target
WORKDIR /app
COPY prisma/schema.prisma ./prisma/schema.prisma
COPY package*.json .
RUN npm ci --only=production
COPY --from=builder /app/dist/apps/${target} ./dist
EXPOSE 3000
CMD ["npm", "run", "start:prod"]
