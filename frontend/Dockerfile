FROM node:20 as base
WORKDIR /app
COPY package*.json ./
RUN npm install

FROM base as dev
COPY . .
EXPOSE 5173
CMD ["npm", "run", "dev", "--", "--host", "0.0.0.0"]

FROM base as build
COPY . .
RUN npm run build
