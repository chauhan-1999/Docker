# Node Base Image
FROM node:latest

#Working Directry
WORKDIR /app

#Copy the Code
COPY . .

#Install the dependecies
RUN npm install
RUN npm run test

#Run the code
CMD ["node","app.js"]
