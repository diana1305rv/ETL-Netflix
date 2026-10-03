# Netflix ETL

Pipeline ETL en Python que limpia el catálogo de Netflix, completa datos faltantes con TMDB y lo carga en MySQL.

## Tecnologías

- Python y Pandas
- TMDB API
- Countries Now API
- MySQL y SQLAlchemy

## Estructura

```text
netflix_titles.csv   # Dataset de entrada
netflix_etl.ipynb    # Pipeline ETL
.env.example         # Variables requeridas
requirements.txt     # Dependencias
```

## Uso

1. Crea y activa un entorno virtual.
2. Instala las dependencias:

   ```bash
   pip install -r requirements.txt
   ```

3. Copia `.env.example` como `.env` y completa tus credenciales de TMDB y MySQL.
4. Configura el esquema MySQL y ejecuta `netflix_etl.ipynb`.

## Configuración

El archivo `.env` debe contener `TMDB_API_KEY` y las variables `MYSQL_*`. Consulta `.env.example` como referencia. No subas este archivo a GitHub.

La carga espera las tablas `ratings`, `directors`, `actors`, `countries`, `genres`, `shows` y sus tablas puente correspondientes.

## Fuente de datos

El dataset base es [Netflix Movies and TV Shows](https://www.kaggle.com/datasets/shivamb/netflix-shows). [TMDB](https://developer.themoviedb.org/docs/getting-started) completa director, reparto y países cuando faltan; [Countries Now](https://countriesnow.space/) normaliza los nombres de países. Las consultas y resultados se guardan en una caché local.
