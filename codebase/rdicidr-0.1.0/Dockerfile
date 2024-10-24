FROM node:15 as builder

WORKDIR ./codebase/rdicidr-0.1.0/

COPY package*.json ./

RUN npm install

COPY ..

RUN npm run build

FROM node:15

WORKDIR /app

COPY --from=builder /app /app

RUN npm install --only=production

ENTRYPOINT ["npm", "start"]