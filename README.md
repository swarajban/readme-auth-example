# readme-auth Example
Sample implementation of 3rd-party server authenticating ReadMe Developer Hub using the 
[ReadMe auth node package](https://github.com/swarajban/readme-auth-dev)

## Installation
```
$ ./build_me.sh
```

This installs npm dependencies, transpiles JS, & copies over *.jade templates to from `src/` to `/dist`.

## Usage
  1. Set the `README_PROJECT_URL` env variable in `.env` based on your ReadMe project's URL. Usually something like `myproject.readme.io`
  1. Set the `README_PROJECT_SECRET` env variable in `.env` based on your ReadMe project's secret in the admin dashboard
  1. Start `readme-auth-example`'s server with
    
    ```
    $ ./run_me.sh
    ```
    This starts the node express server on port 8080
  1. Go to [http://localhost:8080](http://localhost:8080)
  1. Click Login button and login with credentials:
    - email: owlbert@readme.io
    - password: 0wlb3r7
  1. Click `/docs` link and click `Go to ReadMe Docs` button
  1. You will now be logged in to your ReadMe developer hub with the user from this project!
  
