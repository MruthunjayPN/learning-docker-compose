FROM node:20-alpine

WORKDIR /app

COPY package*.json  ./
RUN npm install

COPY . .


# ENV DATABASE_URL="postgresql://postgres:secretpassword@localhost:5432/postgres"
# RUN npx prisma migrate dev
RUN npx prisma generate
RUN npm run build

CMD ["npm", "run", "dev:docker"]