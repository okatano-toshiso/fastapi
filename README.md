# fastapi Build App Steps

## STEP 1

Navigate to the project folder
```
cd fastapi
```

## STEP 2

Activate the virtual environment
```
.venv\Scripts\activate
```
## STEP 3

Install the required libraries
```
pip install -r requirements.txt
```

## STEP 4

Run the app in the environment
```
uvicorn app.main:app --reload
```
<br><br>

# fastapi Build Database Steps

## STEP 1
Start the Docker database
```
docker-compose up -d
```

## STEP 2
Reset the tables
```
alembic downgrade base
```

## STEP 3

Create the initial tables
```
alembic upgrade head
```


