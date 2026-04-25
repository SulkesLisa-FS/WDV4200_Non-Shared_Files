# DEMO PURPOSE ONLY

### Secure Application Development

Node Secrets Assignment: Scenario 3 - Non Shared Files <br>
April 25, 2026 <br>
This app is a **Code Secret Demo - Using Fake Secrets.**




# Scenario 3 — Non-Shared Files

This repository demonstrates the **correct** way to handle secrets:
the application code is shared, but the secrets are **not shared**. 

A `.env` file is required to run the app, but it is not shared in the repository
by adding `.env` to `.gitignore`. Each developer creates their own `.env` locally using their own secret keys.





### Requirements

If you clone this repo and try to run it without a `.env` file, the app
will exit with an error. To run it, create a `.env` file in the project
root with the following variables:

    `NODE_ENV=development`
    `API_KEY=<your-api-key-here>`


- Node.js (latest LTS)
- .gitignore with .env listed

Once you cd into the application root directory follow these steps:

1.  Create the `.env` file for environment variables

        touch .env

2.  Add the environment variable and secret key. (API_KEY can be anything you want)

        # Environmental and Secret Keys (Not Shared)
        NODE_ENV=development
        API_KEY=<your-api-key-here>

3.  Install Dependencies

        npm install

4.  Run the simple server application

        node app.js

5.  TEST In the browser

    `http://127.0.0.1:3000`  


<br>

## Outcomes:

1. The terminal should display the secret variables and their values.

```bash
    NODE_ENV: development
    API_KEY : <your-api-key-shows-here>
```

2. The browser will display the secret variables and application files.

```browser

    Environment: development
    API Key    : <your-api-key-shows-here>
    -----------------------------
    Files in directory:
    - .env
    - .git
    - .gitignore
    - README.md
    - app.js
    - node_modules
    - package-lock.json
    - package.json

```

<br>

## Why the `.` in front of the filename?

File names that begins with a `.` are treated as **hidden file**. 
It does not appear in default directory listings when using `ls` or file managers because it is hidden. <br> 

The dot itself provides no security, it is
more of a display option, but it signals to the user that the file
is configuration rather than application content such as an `.env` file. 

## Why using an `.env` file to hide secrets is best practice?
- Secrets never enter the repository or git history.
- Each environment (dev, staging, prod) can have its own values.
- Rotating a secret does not require a code change.
- The repo can be made public without leaking credentials.
