FROM node:9.10.1-alpine

RUN apk --update add bash

RUN adduser -D -s /bin/false app && npm install --global npm@5.8.0 webpack@4.5.0 webpack-cli@2.0.14
RUN mkdir /app && chown app:app /app
USER app

WORKDIR /app

RUN npm init -y
RUN npm install --save react@16.3.1 react-dom@16.3.1

RUN npm install --save-dev webpack@4.5.0
RUN npm install --save-dev babel-loader@7.1.4
RUN npm install --save-dev babel-core@6.26.0
RUN npm install --save-dev babel-preset-env@1.6.1
RUN npm install --save-dev babel-preset-react@6.24.1
RUN npm install --save-dev eslint@4.19.1
RUN npm install --save-dev eslint-loader@2.0.0
RUN npm install --save-dev babel-eslint@8.2.2
RUN npm install --save-dev redux@3.7.2
RUN npm install --save-dev react-redux@5.0.7
RUN npm install --save-dev prop-types@15.6.1

COPY ./.eslintrc /app/.eslintrc
COPY ./webpack.config.js /app/webpack.config.js

CMD ["webpack"]
