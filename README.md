# Proyecto DevOps - Infraestructura en AWS EC2

Este proyecto implementa una infraestructura moderna con Docker Swarm, CI/CD con Jenkins, monitoreo con Prometheus y Grafana, y una base de datos PostgreSQL.

## Tecnologías utilizadas

- AWS EC2 (Ubuntu 26.04)
- Docker / Docker Swarm
- Jenkins
- Prometheus + Node Exporter
- Grafana
- PostgreSQL + Adminer
- Bootstrap 5

## Estructura del repositorio

- `index.html`: Aplicación web con login y dashboard de control.
- `Dockerfile`: Para construir la imagen de la aplicación.
- `docker-compose.yml`: Despliegue del servicio web en Swarm.
- `prometheus.yml`: Configuración de Prometheus.
- `scripts/deploy.sh`: Script para actualizar el servicio web.

## Instrucciones de despliegue

1. Clonar el repositorio en la máquina de desarrollo.
2. Construir la imagen: `docker build -t tu-usuario/proyecto-devops:latest .`
3. Subir a Docker Hub: `docker push tu-usuario/proyecto-devops:latest`
4. En la EC2, ejecutar: `docker stack deploy -c docker-compose.yml web`

## Monitoreo

- Prometheus: `http://IP_EC2:9090`
- Grafana: `http://IP_EC2:3000` (login admin/admin, luego cambiar contraseña)
- Node Exporter métricas: `http://IP_EC2:9100/metrics`

## Base de datos

- PostgreSQL en contenedor: usuario `admin`, contraseña `admin123`, base `mydb`.
- Adminer: `http://IP_EC2:8081`

## CI/CD

Jenkins ejecuta un pipeline que construye la imagen, la sube a Docker Hub y actualiza el servicio Swarm automáticamente.

## Créditos

Facultad de Ingeniería
Ingeniería en Sistemas de Información y Ciencias de la Comunicación 
7mo semestres.
