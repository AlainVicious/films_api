# FILMS API
## descripcion
API REST en Flask utilizando las extensiones Flask-Restful y Flask-Marshmallow (basada en Marshmallow)

## Extensiones a utilizar
Para crear el API, además de Flask, haremos uso de las siguientes extensiones:

* Flask Restful: Es una extensión que permite generar APIs REST muy fácilmente. Además, viene con un montón de utilidades.
* Flask SQLAlchemy: Para interactuar con la base de datos a través de su ORM. Puedes encontrar más información aquí.
* Flask Migrate: Esta extensión permite generar las tablas de la base de datos a partir de ficheros de migración. Puedes encontrar más información aquí.
* Flask Marshmallow: Es una extensión que facilita la serialización de los modelos de la base de datos a JSON y viceversa. Está basada en Marshmallow.
* Marshmallow SQLAlchemy: Para integrar Flask Marshmallow con SQLAlchemy.

## instalacion
* crear entorno virtual (recomendado)
```
PS $> pip install virtualenv
PS $> python -m venv venv\
PS $> .\venv\Scripts\activate
```
* instalar dependencias
```
PS $> pip install -r requeriments.txt 
```
* crear variables de entorno
```
PS $> set FLASK_APP=entrypoint:app
PS $> set FLASK_ENV=development
PS $> set APP_SETTINGS_MODULE=app.config.default
```
* inicializar db
```
PS $> flask db init
PS $> flask db migrate -m "Initial_db"
PS $> flask db upgrade
```
## Ejecucion
``` 
PS $> flask run
```
## pruebas
### ```POST: http://localhost:5000/api/v1.0/films/``` 
```
{
    "title": "Forrest Gump",
    "length": 8520,
    "year": 1994,
    "director": "Robert Zemeckis",
    "actors": [
        { "name": "Tom Hanks"},
        { "name": "Robin Wright"},
        { "name": "Gary Sinise"},
        { "name": "Mykelti Williamson"},
        { "name": "Sally Field"},
        { "name": "Michael Conner Humphreys"}
    ]
}
```
### ```GET: http://localhost:5000/api/v1.0/films/``` 
```
[
    {
        "year": 1994,
        "actors": [
            {
                "name": "Gary Sinise",
                "id": 3
            },
            {
                "name": "Michael Conner Humphreys",
                "id": 6
            },
            {
                "name": "Mykelti Williamson",
                "id": 4
            },
            {
                "name": "Robin Wright",
                "id": 2
            },
            {
                "name": "Sally Field",
                "id": 5
            },
            {
                "name": "Tom Hanks",
                "id": 1
            }
        ],
        "length": 8520,
        "id": 1,
        "director": "Robert Zemeckis",
        "title": "Forrest Gump"
    }
]
```

### ```GET: http://localhost:5000/api/v1.0/films/1``` 
```
{
    "year": 1994,
    "actors": [
        {
            "name": "Tom Hanks",
            "id": 1
        },
        {
            "name": "Robin Wright",
            "id": 2
        },
        {
            "name": "Gary Sinise",
            "id": 3
        },
        {
            "name": "Mykelti Williamson",
            "id": 4
        },
        {
            "name": "Sally Field",
            "id": 5
        },
        {
            "name": "Michael Conner Humphreys",
            "id": 6
        }
    ],
    "length": 8520,
    "id": 1,
    "director": "Robert Zemeckis",
    "title": "Forrest Gump"
}
```

