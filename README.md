# Docker recipes

[![code style: prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg)](https://github.com/prettier/prettier)
[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/malcodeman/docker-recipes/blob/master/LICENSE)

These are some use cases and code snippets to get you started with Docker.

## Recipes

### python

```
FROM python:3-alpine
RUN pip install --upgrade pip
RUN mkdir /src
ADD . .
WORKDIR /src
RUN pip install -r requirements.txt
CMD gunicorn --bind 0.0.0.0:$PORT wsgi
```

### node

```
FROM node:12-alpine
WORKDIR /app
COPY package.json ./
COPY yarn.lock ./
RUN yarn install --production
COPY . .
EXPOSE 8000
CMD node server.js
```

## License

[MIT](./LICENSE)
