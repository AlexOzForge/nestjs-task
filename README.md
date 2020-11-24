# NestJS Task

## Goal (API only)

Web app where users can create blog posts and view them

## App workflow overview

1. User registers onto the app
2. User obtains JWT token from login method or directly from registration method
3. User could create new BlogPost
4. User could View/Edit/Delete their existing BlogPosts
5. User logs out from the app

## Entities

### User

Field name | Field type | Notes
--- | --- | ---
id | string
username | string
password | string | nobody could see it, should be hashed
first_name | string
last_name | string

### BlogPost

Field name | Field type | Notes
--- | --- | ---
id | string
title | string
content | string
creator_id | string | id of User, who created this post


## Special Requirements

App should have Auth system, made with Passport. 
On User login they get stored User object and [JWT token](https://docs.nestjs.com/security/authentication#jwt-functionality), that they use for onward requests. 

*!* Only login and register routes are public, you could do that via NestJS Guards (this particular thing is described at their [authentication documentation](https://docs.nestjs.com/security/authentication))

## Tech stack

- [NestJS](https://github.com/nestjs/nest) as main framework;
- [Passport](http://www.passportjs.org/) for Authentication (or you could use Nest adapters for it, see [docs](https://docs.nestjs.com/security/authentication));
- MongoDB as data storage;
- Any MongoDB driver you want.
