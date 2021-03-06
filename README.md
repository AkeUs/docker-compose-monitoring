# Stack de Monitoreo

Este archivo crea una infraestrutura de monitoreo local para pruebas con las siguietes aplicaciones:

- Jaeger
- Prometheus
- Loki
- Grafana

para ingresar a Jaeger y Grafana es en las siguientes urls:

- [Jaeger UI](http://localhost:16686)
- [Grafana](http://localhost:3000)

Para crear los **DataSources** en Grafana se tienen que agregar las urls con los nombres de los servicios de Docker Compose.

- Prometheus: <http://prometheus:9090>
- Loki: <http://loki:3100>

Para Prometheus se debera modificar el archivo _prometheus.yml_ con el nombre de la aplicacion y la url del contenedor.

``` yml
scrape_configs:
  - job_name: 'app-name'
    static_configs:
      - targets: ['127.0.0.1:80']
```

Para levantar el ambiente local se ejecuta la siguiente linea.

``` bash
docker-compose up -d
```
