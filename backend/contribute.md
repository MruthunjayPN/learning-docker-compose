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
 - install docker
 - create network - (`docker network create app_network`)
 - start postgres - (`docker run --network app_network --name postgresnewDb -e POSTGRES_PASSWORD=secretpassword -d -p 5432:5432 postgres`)
 - build the image for backend - `docker build --network=host -t eg-backend . `
 - start the image - `docker run -e DATABASE_URL="postgresql://postgres:secretpassword@postgresnewDb:5432/postgres" --network app_network -p 3000:3000 eg-backend`

## Docker compose (Recommended)
 - install docker and docker-compose
 - RUN `docker-compose up`

The Docker Compose setup will:
1. Start PostgreSQL database
2. Wait for database to be ready (health check)
3. Start the backend service
4. Run migrations automatically
5. Start the application