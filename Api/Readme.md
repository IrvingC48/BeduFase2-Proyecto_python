# Creación de api

## Razón
Como se menciona en el documento la razón de la creación de una `API` fue con un fin totalmente didáctico, para poder aplicar lo aprendido en las sesiones del módulo de python, ya que no existe una `API` oficial para obtener los datos.
## Dependencias
Depenciandas de python utilizadas 

> **Nota:** la versión de python utilizada para el desarrollo es **3.9**

- **Flask** como framework web escrito en python para el desarrollo de la api [![flask](https://img.shields.io/badge/flask-v%201.1.2-blue)](https://pypi.org/project/Flask/) 
- **Mongodb Atlas** para el almacenamiento de datos en cloud
- **Google Cloud** para el deploy de la app

## Uso
Ejemplo de uso de la api

> [GET] Consulta para todos los datos de PM2.5 del 2019

```python
import requests as res
import pandas as pd

endpoint = 'http://34.73.220.231/api/dpmdos/primer_año_all'
r = res.get(endpoint)
r.status_code

json = r.json()
normalized = pd.json_normalize(json)
df = pd.DataFrame.from_dict(normalized)
df.head()
```