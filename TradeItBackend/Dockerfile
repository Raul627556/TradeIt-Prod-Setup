# Etapa de build
FROM node:18 as build

WORKDIR /app

COPY package.json package-lock.json ./
RUN npm install

COPY . .

# Etapa de producción
FROM node:18-slim

WORKDIR /app

COPY --from=build /app /app

# Solo expone puerto 9001 (el de la API)
EXPOSE 9001

CMD ["node", "index.js"]
