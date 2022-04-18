1. Choice of the base image on which to build each container.  
  i.) backend-image - This has been created with the mongo-express base image due to the apps use of the mongodb database
  ii.) client-image - This has been created with the node-alpine base image because the app is built on node platform and the alpine version is light which will make the built container to be light i.e less megabytes  
    
2. Dockerfile directives used in the creation and running of each container.  
   i.) backend - Dockerfile  
   FROM mongo-express - base image  

   RUN mkdir /backend - create a folder in the container named backend  

   WORKDIR /backend - make the /backend folder the working directory to execute the following commands  

   COPY package-lock.json /backend/ - copy the file to backend so as to guide the npm install on what packages to install  

   COPY package.json /backend/ - copy the file to backend so as to guide the npm install on what packages to install    

   RUN npm install  - install the npm packages as guided by the json files  

   COPY . . - Copy all directories in the base folder on backend to the base folder inside the container  

   CMD ["npm","start"]  - start the app after running the container  

  ii.) client-Dockerfile  
  FROM node:12-alpine - base image required  

  RUN mkdir /client - create a client directory in the container  

  WORKDIR /client - make the client directory the working directory  

  COPY . . - Copy all files in the base folder to the working directory in the container

  RUN npm i npm@latest -g - install the latest npm package and make it global

  RUN npm install - install the npm modules required 

  RUN npm install webpack - install webpack package

  EXPOSE 3000 - expose port 3000 outside the container

  CMD ["npm","start"] - run the command after the container is created.