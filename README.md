


## Tools used
- Python 3.6.4
- Virtualenv & [autoenv](https://github.com/kennethreitz/autoenv)
- Flask
- Gunicorn
- Heroku
- Git & Github


## Staging/Production Workflow

1. Run app locally to ensure it works - `python app.py` on URL `http://localhost:5000/`.
2. Add changes to git: `git add .`
3. Commit changes: `git commit -m "Some commit message"`
4. Push to Heroku: `git push stage master`, and `git push pro master`
5. Push to Github: `git push`

## Configuration Environments

### Local Settings

In a `.env` file (see `autoenv`) we have:
```
source env/bin/activate
export APP_SETTINGS="config.DevelopmentConfig"
```

Automatically starts the virtual environment when entering the directory, and sets the DevelopmentConfig environment variables.

## Heroku Settings

For staging run the following command: 
```bash
$ heroku config:set APP_SETTINGS=config.StagingConfig --remote stage
```

For production:
```bash
$ heroku config:set APP_SETTINGS=config.ProductionConfig --remote pro
```

And in `app.py`:
```python
...
app = Flask(__name__)
app.config.from_object(os.environ['APP_SETTINGS'])
...
```

## Heroku Links

...

## Other Resources

[Tutorial followed - Done!](https://realpython.com/flask-by-example-part-1-project-setup/)
[Next](https://realpython.com/flask-by-example-part-2-postgres-sqlalchemy-and-alembic/)

- Explore - https://mdyzma.github.io/2017/05/20/flask-and-travis-ci/
- http://docs.python-guide.org/en/latest/writing/tests/
- 



