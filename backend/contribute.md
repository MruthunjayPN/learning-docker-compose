## Manual Installation
 - install node.js locally
 - clone the repo
 - install dependencies - npm install
 - start the db locally 
        -(`docker run -e POSTGRES_PASSWORD=secretpassword -d -p 5432:5432 postgres` )
 - update .env file
 - npx prisma migrate
 - npx prisma generate
 - npm run build
 - npm run start

## Docker installation
 - if we do using only docker , we have to start 2 services with docker - backend and postgress -- this may increase for  large applications . so we will use docker-compose

 - install docker
 - start postgres - (`docker run -e POSTGRES_PASSWORD=secretpassword -d -p 5432:5432 postgres`)
 - build the image for backend - `docker build -t  eg-backend . `
 - start the image - `docker run -p 3000:3000 eg-backend`

 ## Docker compose
 - install docker , docker-compose
 - RUN `docker-compose up `

 - number of steps with docker compose remain same (even if num of services increase)