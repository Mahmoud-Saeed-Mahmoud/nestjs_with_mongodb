<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo-small.svg" width="120" alt="Nest Logo" /></a>
</p>

[circleci-image]: https://img.shields.io/circleci/build/github/nestjs/nest/master?token=abc123def456
[circleci-url]: https://circleci.com/gh/nestjs/nest

  <p align="center">A progressive <a href="http://nodejs.org" target="_blank">Node.js</a> framework for building efficient and scalable server-side applications.</p>
    <p align="center">
<a href="https://www.npmjs.com/~nestjscore" target="_blank"><img src="https://img.shields.io/npm/v/@nestjs/core.svg" alt="NPM Version" /></a>
<a href="https://www.npmjs.com/~nestjscore" target="_blank"><img src="https://img.shields.io/npm/l/@nestjs/core.svg" alt="Package License" /></a>
<a href="https://www.npmjs.com/~nestjscore" target="_blank"><img src="https://img.shields.io/npm/dm/@nestjs/common.svg" alt="NPM Downloads" /></a>
<a href="https://circleci.com/gh/nestjs/nest" target="_blank"><img src="https://img.shields.io/circleci/build/github/nestjs/nest/master" alt="CircleCI" /></a>
<a href="https://coveralls.io/github/nestjs/nest?branch=master" target="_blank"><img src="https://coveralls.io/repos/github/nestjs/nest/badge.svg?branch=master#9" alt="Coverage" /></a>
<a href="https://discord.gg/G7Qnnhy" target="_blank"><img src="https://img.shields.io/badge/discord-online-brightgreen.svg" alt="Discord"/></a>
<a href="https://opencollective.com/nest#backer" target="_blank"><img src="https://opencollective.com/nest/backers/badge.svg" alt="Backers on Open Collective" /></a>
<a href="https://opencollective.com/nest#sponsor" target="_blank"><img src="https://opencollective.com/nest/sponsors/badge.svg" alt="Sponsors on Open Collective" /></a>
  <a href="https://paypal.me/kamilmysliwiec" target="_blank"><img src="https://img.shields.io/badge/Donate-PayPal-ff3f59.svg" alt="Donate us"/></a>
    <a href="https://opencollective.com/nest#sponsor"  target="_blank"><img src="https://img.shields.io/badge/Support%20us-Open%20Collective-41B883.svg" alt="Support us"></a>
  <a href="https://twitter.com/nestframework" target="_blank"><img src="https://img.shields.io/twitter/follow/nestframework.svg?style=social&label=Follow" alt="Follow us on Twitter"></a>
</p>
  <!--[![Backers on Open Collective](https://opencollective.com/nest/backers/badge.svg)](https://opencollective.com/nest#backer)
  [![Sponsors on Open Collective](https://opencollective.com/nest/sponsors/badge.svg)](https://opencollective.com/nest#sponsor)-->

## NestJS MongoDB Authentication API

A robust authentication system built with NestJS, MongoDB, and JWT, featuring user management and post creation capabilities. This project was developed using [Windsurf](https://codeium.com/windsurf), the world's first agentic IDE.

## Features

- User Authentication
  - JWT-based authentication
  - Secure password hashing with bcrypt
  - Login and registration endpoints
  - Protected routes

- User Management
  - Create, read, update, and delete users
  - Email validation
  - Password validation

- Post Management
  - Create, read, update, and delete posts
  - Posts associated with users
  - Protected post endpoints

## Prerequisites

- Node.js (v14 or later)
- MongoDB database
- npm or yarn package manager

## Environment Variables

Create a `.env` file in the root directory with the following variables:

```env
DATABASE_URL="mongodb+srv://your-username:your-password@your-cluster-url/your-database?retryWrites=true&w=majority"
JWT_SECRET="your-jwt-secret"
PORT=3333
```

## Installation

```bash
# Install dependencies
$ npm install

# Push database schema
$ npx prisma db push

# Generate Prisma client
$ npx prisma generate
```

## Running the app

```bash
# development
$ npm run start

# watch mode
$ npm run start:dev

# production mode
$ npm run start:prod
```

## API Documentation

Once the application is running, visit `http://localhost:3333/api` to access the Swagger documentation.

### Authentication Endpoints

- POST `/auth/register` - Register a new user
- POST `/auth/login` - Login and receive JWT token

### Protected Endpoints (Requires JWT Token)

Users:
- GET `/users` - Get all users
- GET `/users/:id` - Get user by ID
- PATCH `/users/:id` - Update user
- DELETE `/users/:id` - Delete user

Posts:
- GET `/posts` - Get all posts
- GET `/posts/:id` - Get post by ID
- POST `/posts` - Create new post
- PATCH `/posts/:id` - Update post
- DELETE `/posts/:id` - Delete post

## Security Features

- Password hashing using bcrypt
- JWT token authentication
- Protected routes with Guards
- Input validation using class-validator
- Swagger API documentation with bearer auth

## Project Structure

```
src/
├── auth/              # Authentication module
├── users/             # Users module
├── posts/             # Posts module
├── prisma/            # Prisma schema and migrations
└── main.ts            # Application entry point
````

## Testing

```bash
# unit tests
$ npm run test

# e2e tests
$ npm run test:e2e

# test coverage
$ npm run test:cov
```

## License

This project is [MIT licensed](LICENSE).
