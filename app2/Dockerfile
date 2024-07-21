FROM node

WORKDIR /app2

COPY ["package.json", "package-lock.json*", "./"] 

RUN npm install

COPY . .

EXPOSE 4001

CMD [ "npm", "start"]

# docker buildx build -t tu_nombre_de_imagen . --load