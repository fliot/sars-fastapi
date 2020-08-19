# Backend

## Dev Instructions

### Dev Tools
Run `pipenv install --dev` to install the env.
Run `pipenv run pre-commit install` to initialize the git hooks.
Run `pipenv run pre-commit run --all-files` if there are file that were committed before adding the git hooks.
Activate the shell with: `pipenv shell`
Lint with: `pylint app` and `pylint load.py`

### Start without Docker Compose (Dev)
Run this inside the pipenv shell:

```
export MYSQL_PASSWORD=password
export MYSQL_DATABASE=database
export DB_CONN=mysql+pymysql://root:$MYSQL_PASSWORD@$localhost:3306/$MYSQL_DATABASE
docker run --name mysql -e MYSQL_ROOT_PASSWORD=$MYSQL_PASSWORD -e MYSQL_DATABASE=$MYSQL_DATABASE -p 3306:3306 -d mysql:5.7
python load.py
uvicorn app.main:app
```


#### Get and Start MySQL Container
`docker pull mysql:5.7`
