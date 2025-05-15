# Guía para Configuración y Uso del Ejemplo 

---
## Paso 1: Verificar la instalacion de herramientas

Antes de iniciar, asegúrate de tener instalado y configurado:

>Docker y Docker Compose

>Git

Puedes verificarlo con los estos comandos:

```bash
docker --version
git --version
```
caso contrario instalar estas herramientas, te dejo los links debajo:
#### Git hub
[https://git-scm.com/downloads/win]
### Docker

[https://www.docker.com/]

---

## Paso 2: Clonar el Repositorio Remoto

Clonar el repositorio oficial desde GitHub:

```bash
git clone https://github.com/pum3ucatec/sig2.git
```

---
## Paso 3: Directorio del ejemplo

```bash
cd ejemplos/e1-sqlserver
```
---
## Paso 4: Levantar los contenedores con Docker Compose
Ejecutar Docker Compose para iniciar los contenedores:

```bash
docker compose up -d
```
---
## Paso 5: Verificar contenedores activos

```bash
docker ps
```
---
## Paso 6: Probar la Conexión al contenedor SQL Server

#### Windows
```bash
winpty docker exec -it container_name /opt/mssql-tools18/bin/sqlcmd -S localhost -U SA -P "your_password" -C -d master -Q "SELECT name FROM sys.databases;"
```
#### Linux

```bash
docker exec -it container_name /opt/mssql-tools18/bin/sqlcmd -S localhost -U SA -P "your_password" -C -d master -Q "SELECT name FROM sys.databases;"
```
---
## Paso 7: Crear y Cambiar a una nueva rama en GitHub

```bash
git checkout -b NombreApellido/Practica1
```
---
## Paso 8: Para finalizar

Antes de hacer commits, siempre verifica el estado con:

```bash
git status
```
Verificamos nuestra rama con:

```bash
git branch
```
Al finalizar el trabajo, no olvides subir tus cambios:

```bash
git add .
git commit -m "Descripción"
git push origin NombreApellido/Practica1
```
---
### Tarea finalzada

![tarea 1](.\Imagenes\tarea1.png)
