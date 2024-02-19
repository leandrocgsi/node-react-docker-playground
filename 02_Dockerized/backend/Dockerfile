FROM node:14.15.0
WORKDIR /app
COPY ["package.json", "package-lock.json", "wait-for.sh", "startup.sh", "./"]
RUN echo "deb http://deb.debian.org/debian buster main" > /etc/apt/sources.list
RUN apt-get update  && apt-get install -y netcat -y && chmod +x ./wait-for.sh ./startup.sh && npm install --production
COPY . .
EXPOSE 5000
CMD ["npm", "start"]