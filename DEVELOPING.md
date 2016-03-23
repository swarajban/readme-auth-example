# Developing readme-auth-example

## Installation
```
$ ./build_me.sh
```

This installs npm dependencies, transpiles JS, & copies over *.jade templates to from `src/` to `/dist`.

## Prerequisites
  1. Start ReadMe's server from the [readmeio/readme](https://github.com/readmeio/readme) repo w/ `npm start`
  1. Create a project on your local ReadMe server, activate it (by making it 'Open Source'), and set the project's *JWT Secret* in the *Project Settings* tab
  1. Set the `README_PROJECT_URL` env variable in this repos's `.env` based on your ReadMe project's URL. Usually something like `myproject.readme.io`
  1. Set the `README_PROJECT_SECRET` env variable in this repos's `.env` based on your ReadMe project's secret in the admin dashboard

## How it works
  1. This repo implements a `passport` local auth strategy with users / passwords defined in `src/js/users.js`
  1. Once logged in, the home page renders a link to `/docs`
  1. When rendering `/docs`:
    - The server generates an link to the ReadMe docs with a JWT authentication token using the [readme-auth](https://github.com/swarajban/readme-auth-dev) module
    - The link looks like `http://test-project.readme.local:3000?auth_token=<jwt>`
  1. The ReadMe server finds or creates a ReadMe `Hub2User` based on the ReadMe project & `email` specified in the JWT payload and authenticates the user
  