
# Earthquake data scraper
Проект реализует инфраструктуру для автоматического сбора информации о землятресениях с API [earthquake.usgs.gov](https://earthquake.usgs.gov/)  
Проект развернут с Docker Compose по адресу http://31.128.45.147


## Используемые технологии
- [AirFlow](https://airflow.apache.org/)
- [MinIO](https://www.min.io/)
- [Metabase](https://www.metabase.com/)
- [DuckDB](https://duckdb.org/)
- [Docker](https://www.docker.com/)

## Архитектура
В проекте реализована архитектура Data Lakehouse (Data Lake + DWH).  
Источник данных  - API [earthquake.usgs.gov](https://earthquake.usgs.gov/fdsnws/event/1/#methods).  
Data Lake представлен в виде объектного хранилища данных MinIO, куда изначально поступают данные и сохраняются в формате parquet.  
DWH представляет собой базу данных под управлением PostgreSQL, где определены три слоя: ODS, STG, DM.  
Для загрузки данных из API в Data Lake, а затем в DWH используется СУБД Duckdb.  
Загрузка данных оркестрируется в Apache Airflow при помощи 4 DAG.  
Визуализация данных выполняется при помощи Metabase.  

 <img width="1549" height="610" alt="image" src="https://github.com/user-attachments/assets/ca36557c-ae9d-4deb-9bcb-35445a0bdcdc" />


## Дополнительные ссылки и учетные данные для ознакомления с проектом:
  Airflow: http://31.128.45.147:8080  
  login:readonly  
  password: 123456  

  MinIO: http://31.128.45.147:9000  
  login:readonly  
  password:readonly

  Metabase: http://31.128.45.147:3000/  
  login:readonly@example.com  
  password:IdUGjytQ?9vJzt  
