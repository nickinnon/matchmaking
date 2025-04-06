FROM node:20-alpine AS base
WORKDIR /workspace

COPY package*.json ./
RUN npm ci

FROM base AS dev
CMD ["npm", "run", "dev"]

FROM base AS prod
COPY . .
RUN npm run build
CMD ["npm", "start"]
