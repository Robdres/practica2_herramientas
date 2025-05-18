# Práctica 2
Roberto Alvarado

# Datos
Los datos los puedes encontrar en https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction/data

# Version simplificada en un notebook
Puedes encontrar la version de publicación de datos en mlflow dentro del notebook
[NOTEBOOK](src/main.ipynb)
es un minimo uso de mlflow

# Correr con Docker
La mejor forma de correr es usando Dokcer, todo lo puedes hacer desde el path src
Pasos de uso
```
cd src
docker-compose up --build
```
Despues puedes acceder a los servicios, a veces de los puertos disponibles
pueden cambiar pero para miflow debe ser
```
http://0.0.0.0:9090 para mlflow
```
El host puede cambiar pero el puerto es 9090

Y para la aplicación flask, ahi se debería ver el url que docker envía,
pero el puerto es 8080 y el host funcionaría dependiendo de docker,
por ejemplo, docker comenzó a compartir la app en

```
http://172.18.0.3:8080 para flask app
```

# Correr cada servicio sin docker
También se puede correr cada servicio.
0. Ir al directorio
```
cd src/app
```
1. Instalar requirements
```
pip install --no-cache-dir -r requirements.txt
```
2.Para prender el servidor de mlflow

```
mlflow server --default-artifact-root ./mlruns --host 0.0.0.0 --port 9090
```
2. Para correr el servidor flask en python
```
python3 main.py
```

Estos se pueden acceder en el host localhost

# Notas
Es posible hacer uso de un enviroment con todo instalado sin hacer uso de pip
haciendo source del env en el directorio
