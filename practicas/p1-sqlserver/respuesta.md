# 🐳Práctica 1: Configuración de SQL Server en Docker (Windows 11)
---

## 📋 Requisitos Previos
Debe tener instalado las siguientes herramientas:

  - [**Docker:**](https://www.docker.com/) Para la gestión de contenedores.

  - [**GIT:**](https://git-scm.com/) Para el control de versiones
 
  - [**Github**](https://github.com/) Para almacenar el código de manera remota.

Verificar herramientas instaladas:

Dodcker
```
docker --version
```
GIT
```
git --version
```
## ⚙️ Configuración Inicial del Repositorio

### 1. Clonar repositorio

Inicia clonando el repositorio remoto con el siguiente comando:
``` 
git clone https://github.com/pum3ucatec/sig2.git
```
``` 
cd sig2
```
### 2. Creación de una Rama Personal

Crea una nueva rama para tu práctica y cámbiate a ella:
```
git checkout -b MaideMamani/Practica1
```

### 3. Preparar el entorno de ejecución

Archivos base

- Copiar la carpeta **ejemplos/e1-sqlserver**

- Crear archivos: 
  - respuesta.md
  - .env

### 4. Configuración de variables

1. Editar el archivo .env con:

Abrir el archivo **.env** y añadir la siguiente línea para establecer la contraseña.
```
SA_PASSWORD = "Maide@2025"
```

### 5. Despliegue del Contenedor SQL Server

Ejecutar Docker Compose para iniciar los contenedores:
```
docker compose up -d
```
> Este comando levantará el contenedor en segundo plano, permitiéndote conectarte y realizar consultas en la base de datos.

Verificar contenedores
```
docker ps
```
Consultar a la base de datos, cambiando los datos **nombre** y **contraseña**
```
docker exec -it container_name *//opt/mssql-tools18/bin/sqlcmd -S localhost -U SA -P "your_password" -C -d master -Q "SELECT name FROM sys.databases;"
```
Ejemplo:
```
docker exec -it sqlserver_db "//opt/mssql-tools18/bin/sqlcmd -S localhost -U SA -P "maide@2025" -C -d master -Q "SELECT name FROM sys.databases;"
```
## 💾 Gestión de Cambios con Git

Antes de realizar cualquier modificación, verifica el estado de tu repositorio:
```
git status
```

Agrega todos los cambios realizados:

```
git add .
```
Realiza un commit con un mensaje descriptivo:

```
git commit -m "Practica1_realizada"
```
Finalmente, sube tus cambios a la rama correspondiente en GitHub:

```
git push origin MaideMamani/Practica1
```
### Resultado de la Practica1

![Consola](/practicas/p1-sqlserver/imagen/Docker_C.png)

**NOTA.-**

Durante la práctica, se proporcionó el siguiente comando como ejemplo para conectarse a SQL Server y ejecutar una consulta, sin embargo, el comando daba error al ejecutarse en Windows debido a la forma en que se manejan las rutas y los comandos en este sistema operativo.

Comando
```
docker exec -it container_name /opt/mssql-tools18/bin/sqlcmd -S localhost -U SA -P "your_password" -C -d master -Q "SELECT name FROM sys.databases;"
```
Comando modificado 
```
docker exec -it sqlserver_db "//opt/mssql-tools18/bin/sqlcmd -S localhost -U SA -P "maide@2025" -C -d master -Q "SELECT name FROM sys.databases;"
```
>Al ejecutar el comando modificado, se obtuvo con éxito la lista de bases de datos en el servidor SQL.