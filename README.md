
# Earthquake data scraper
Данный проект реализует инфраструктуру для автоматического сбора информации о землятресениях с сайта [earthquake.usgs.gov](https://earthquake.usgs.gov/)


## Используемые технологии
- [AirFlow](https://airflow.apache.org/)
- [MinIO](https://www.min.io/)
- [Metabase](https://www.metabase.com/)
- [DuckDB](https://duckdb.org/)
- [Docker](https://www.docker.com/)

## Архитектура
В проекте реализуется арихтектура Data Lakehouse (Data Lake + DWH).
Источником данных является API [earthquake.usgs.gov]([https://earthquake.usgs.gov/](https://earthquake.usgs.gov/fdsnws/event/1/#methods).
Data Lake представлен в виде объектного хранилища данных MinIO, куда изначально поступают данные.
DWH предствляет собой базу данных под управлением PostgreSQL, где определены три слоя: ODS,STG,DM.
Для осуществления загрузки данных из API в Data Lake а затем в DWH используется СУБД Duckdb.
Процессы по загрузке данных автоматизированы в Apache Airflow.
В качестве BI системы выбран MetaBase.

<img width="1549" height="610" alt="image" src="https://github.com/user-attachments/assets/c0f96f4c-dde6-41e8-9c24-f03691693de3" />


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

