FROM node as base

FROM base as development

WORKDIR /app
ENV REACT_APP_API_PORT=8080
COPY package.json .

RUN npm install

COPY . .

EXPOSE 80

CMD [ "npm", "start" ]

FROM base as production

WORKDIR /app
COPY package.json .
RUN npm install --only=production
COPY . .
EXPOSE 3000
CMD ["npm","start"]