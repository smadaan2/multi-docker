# Multistep build process
FROM node:alpine as builder
WORKDIR '/app'
COPY ./package.json ./
RUN npm install
COPY . .
RUN npm run build  #output will build folder which is placed under /app/build path

# /app/builder   <-- all the stuff

FROM nginx
#Change defaultport i.e 80 to 3000 
EXPOSE 3000  
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
#Copying output of Ist phase to nginx path
COPY --from=builder /app/build /usr/share/nginx/html