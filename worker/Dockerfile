# Specify base image
FROM node:alpine

#Specify working directory
WORKDIR "/app"

#Install Dependencies
COPY package.json . 
RUN npm install
COPY . .

# Specify default command run when container start
CMD ["npm", "run", "start"]