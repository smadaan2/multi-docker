FROM node:alpine
WORKDIR '/app'
COPY ./package.json ./
# Install dependencies
RUN npm install       
COPY . .
# Run startup command
CMD ["npm", "run", "start"]