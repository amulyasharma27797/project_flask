# project_flask

```pip install -r requirements.txt```

To run the application:
```python run.py```

#### Logger In Application
```
Application uses an in-built logger system
which handles the logs generated in the application.
A log file for each day is maintained for a week.
``` 
```
Suppose you want to use it in form validation during signin
for logging wrong email or password.

 - from app import app

Use this line at appropriate place under signin method

 - app.logger.error("Wrong email or password")
```






## Using Response

In any part of the project, import success or failure from app

```from app import success, failure```

Usage:

Success

```return success(data=<YOUR_VALUE>)```

Failure/Error

```return failure(message=<YOUR_VALUE>)```


## Environments

To setup environments create a file with the environment name.
Example: `local.env`
```.env
DEBUG = True

# Define the database
SQLALCHEMY_DATABASE_URI = "sqlite:///${HOME}/Desktop/app.db"
SQLALCHEMY_TRACK_MODIFICATIONS = False
DATABASE_CONNECT_OPTIONS = {}

THREADS_PER_PAGE = 2
CSRF_ENABLED = True

# Use a secure, unique and absolutely secret key for
# signing the data.
CSRF_SESSION_KEY = "M0n3Y_H3!5T"
SECRET_KEY = "M0n3Y_H3!5T"
JWT_SECRET_KEY = "M0n3Y_H3!5T"

AUTH_TOKEN_TTL_MINUTES = 60

# Hooks
HOOKS_REQUIRED = True

# Logs
LOG_LEVEL = 'DEBUG'
LOG_FILE_PATH = "app/logger/logs"
```

Now, set the `FLASK_ENV` as `local` to use the `local.env` configuration.
