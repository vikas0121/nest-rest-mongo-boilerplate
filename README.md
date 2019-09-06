<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo_text.svg" width="320" alt="Nest Logo" /></a>
</p>

[travis-image]: https://api.travis-ci.org/nestjs/nest.svg?branch=master
[travis-url]: https://travis-ci.org/nestjs/nest
[linux-image]: https://img.shields.io/travis/nestjs/nest/master.svg?label=linux
[linux-url]: https://travis-ci.org/nestjs/nest

  <p align="center">A progressive <a href="http://nodejs.org" target="blank">Node.js</a> framework for building efficient and scalable server-side applications, heavily inspired by <a href="https://angular.io" target="blank">Angular</a>.</p>
    <p align="center">
<a href="https://www.npmjs.com/~nestjscore"><img src="https://img.shields.io/npm/v/@nestjs/core.svg" alt="NPM Version" /></a>
<a href="https://www.npmjs.com/~nestjscore"><img src="https://img.shields.io/npm/l/@nestjs/core.svg" alt="Package License" /></a>
<a href="https://www.npmjs.com/~nestjscore"><img src="https://img.shields.io/npm/dm/@nestjs/core.svg" alt="NPM Downloads" /></a>
<a href="https://travis-ci.org/nestjs/nest"><img src="https://api.travis-ci.org/nestjs/nest.svg?branch=master" alt="Travis" /></a>
<a href="https://travis-ci.org/nestjs/nest"><img src="https://img.shields.io/travis/nestjs/nest/master.svg?label=linux" alt="Linux" /></a>
<a href="https://coveralls.io/github/nestjs/nest?branch=master"><img src="https://coveralls.io/repos/github/nestjs/nest/badge.svg?branch=master#5" alt="Coverage" /></a>
<a href="https://gitter.im/nestjs/nestjs?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=body_badge"><img src="https://badges.gitter.im/nestjs/nestjs.svg" alt="Gitter" /></a>
<a href="https://opencollective.com/nest#backer"><img src="https://opencollective.com/nest/backers/badge.svg" alt="Backers on Open Collective" /></a>
<a href="https://opencollective.com/nest#sponsor"><img src="https://opencollective.com/nest/sponsors/badge.svg" alt="Sponsors on Open Collective" /></a>
  <a href="https://paypal.me/kamilmysliwiec"><img src="https://img.shields.io/badge/Donate-PayPal-dc3d53.svg"/></a>
  <a href="https://twitter.com/nestframework"><img src="https://img.shields.io/twitter/follow/nestframework.svg?style=social&label=Follow"></a>
</p>
  <!--[![Backers on Open Collective](https://opencollective.com/nest/backers/badge.svg)](https://opencollective.com/nest#backer)
  [![Sponsors on Open Collective](https://opencollective.com/nest/sponsors/badge.svg)](https://opencollective.com/nest#sponsor)-->
    
### 📚 Description

This boilerplate is made to quickly prototype backend applications. It comes with database, logging, security, and authentication features out of the box.

---

### 🛠️ Prerequisites

#### Non Docker

- Please make sure to have MongoDB locally, or utilize Mongo on the cloud by configuration a cluster in [atlas](https://www.mongodb.com/cloud/atlas). Then grab the connection string and modify the following [line](https://github.com/msanvarov/nest-mongoose-boilerplate/blob/master/.env.example#L10).

#### Docker :whale:

- Please make sure to have docker dekstop setup on local machine to quickly compose both the mongodb and web application. Then follow the steps outlined below.

---

### :rocket: Setup

#### Manually Deploying without Docker

- Create a .env file using the `cp .env.example .env` command and replace the existing env variables with the correct variables (mongodb url either srv or no auth localhost)
- Install dependencies using `npm i` or `yarn`
- Start the app for pre-production using `npm run start` or for development using `npm run start:dev` (the app will be exposed on the port 9000; not to conflict with React)

#### Deploying with Docker :whale:

- Execute the following command in app directory:

```bash
# creates and loads the docker container with required configuration
$ docker-compose up
# copy the .env file from .env.example
$ docker exec -it nest cp .env .env.example
```

- The following command will setup the project for you (building the Docker images, starting docker-compose stack). The Web application and mongo will exposed on http://localhost:9001 and http://localhost:27017 respectively

### :lock: Environment Configuration

By default the application comes with a config module that can inject the ConfigService and read every environment variable from the .env. file.

**APP_ENV** - the application environment it will be executing as, either in development or production

**APP_URL** - the base url for application

**WEBTOKEN_SECRET_KEY** - the secret key to decrypt web tokens with. Make sure to generate a random alphanumeric string for this.

**WEBTOKEN_EXPIRATION_TIME** - the time in seconds on when the web token will expire; by default it's 1800 seconds which is 30 mins

**DB_URL** - the url to the mongodb collection

---

### :white_check_mark: Testing

#### Docker :whale:

```bash
# unit tests
$ docker exec -it nest yarn test

# e2e tests
$ docker exec -it nest yarn test:e2e

# test coverage
$ docker exec -it nest yarn test:cov
```

#### Non-Docker

```bash
# unit tests
$ npm run test

# e2e tests
$ npm run test:e2e

# test coverage
$ npm run test:cov
```
---

### :bulb: TypeDocs 

The documentation can be generated by typing in `npm run typedocs`. This will produce a **docs** folder with the required files.

```bash
# generate docs for code
$ npm run typedocs
```

---

### :pencil: Open API

Out of the box, the web app comes with an [open api specification](https://swagger.io/specification/), that is used to describe RESTful APIs. Nest provides a dedicated module to work with it.
                                                                                                                                              
The configuration for Swagger can be found at this [location](https://github.com/msanvarov/nest-mongoose-boilerplate/tree/master/src/swagger).

---

### :sparkles: Mongoose

Mongoose creates an abstraction layer over operations on MongoDB. Please view the [documentation](https://mongoosejs.com/) for further details. 

The configuration for Mongoose can be found in the [app module](https://github.com/msanvarov/nest-mongoose-boilerplate/blob/master/src/modules/main/app.module.ts#L15).

___

### :loud_sound: Logs

This boilerplate comes with a winston module for logging, the configurations for winston can be found in the [app module](https://github.com/msanvarov/nest-mongoose-boilerplate/blob/master/src/modules/main/app.module.ts#L24).

---

### Support

Nest is an MIT-licensed open source project. It can grow thanks to the sponsors and support by the amazing backers. If you'd like to join them, please [read more here](https://docs.nestjs.com/support).

---

## License

Nest is [MIT licensed](LICENSE).

[Author](https://msanvarov.github.io/personal-portfolio/)
