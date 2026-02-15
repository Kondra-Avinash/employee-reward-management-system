# Stage 1: Build Angular
FROM node:20-alpine as build

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .
RUN npm run build

# Stage 2: Serve with nginx
FROM nginx:alpine

COPY --from=build /app/dist/reward-system/browser /usr/share/nginx/html

EXPOSE 80
