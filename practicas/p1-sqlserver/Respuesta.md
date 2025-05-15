# Guía Completa: Práctica 1 - Configuración de SQL Server en Docker

## Requisitos Previos
- Docker instalado y en ejecución
- Git instalado
- Cuenta en GitHub
- Docker Compose (v2+ recomendado)

## 1. Configuración Inicial del Repositorio

1. Primero clonar el repositorio remoto

```
git clone https://github.com/pum3ucatec/sig2.git
cd sig2
```

2. Crear y cambiar a tu rama personal

```
git checkout -b MarisolHerrera/Practica1
```

## 2. Preparación del Entorno
Copiar archivos base

1. Copiar lo esencial de la carpeta **ejemplos/e1-sqlserver**

2. Crear el archivo **Respuesta.md** y **.env**

## 3. Configurar variables de entorno

1. Editar el archivo .env con:

```
SA_PASSWORD = "Marisol.2025"
```

## 4. Despliegue del Contenedor SQL Server

1. Conexión y Operaciones en SQL Server

Conectarse al servidor

```
docker-compose up -d
```

![Consola](/practicas/p1-sqlserver/img/IC.png)

2. Ejecucion

Ver contenedores en ejecución

```
docker ps
```

![Consola](/practicas/p1-sqlserver/img/VC.png)

3. Consultar bases de datos

Cambiar los datos necesarios, como el nombre y contraseña

```
docker exec -it container_name /opt/mssql-tools18/bin/sqlcmd -S localhost -U SA -P "your_password" -C -d master -Q "SELECT name FROM sys.databases;"
```

### Ejemplo

```
 docker exec -it sqlserver_db /opt/mssql-tools18/bin/sqlcmd -S localhost -U SA -P "Marisol.2025" -C -d master -Q "SELECT name FROM sys.databases;"
```

![Consola](/practicas/p1-sqlserver/img/CBD.png)

## 5. Gestión de Cambios con Git

1. Verificar estado

```
git status
```

2. Agregar cambios

```
git add .
```

3. Hacer commit

```
git commit -m "Primera practica de SIG 2"
```

4. Subir cambios

```
git push origin MarisolHerrera/Practica1
```

## 6. Notas importantes

### 1. Posibles problemas

1. Problemas con credenciales

Pueden haber problemas con credenciales al momento de enlazar con github, se pueden solucionar con los siguientes comandos:

```
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"
```

Solo debemos reemplazar con nuestros datos reales de la cuenta de Github.

2. Problemas con la contraseña

Este problema ocurre porque GitHub ha dejado de aceptar contraseñas para autenticación y ahora requiere métodos más seguros, se puede configurar Git para usar un token de acceso personal en lugar de contraseña, siguiendo los siguientes pasos:

- Ve a **GitHub Tokens**
- Haz clic en **"Generate new token"**
- Selecciona los scopes necesarios
- Copia el token generado **(sólo se muestra una vez)**

### Configurar repositorio para usar token

```
git remote set-url origin https://TU_USUARIO_GITHUB:TU_TOKEN@github.com/TU_USUARIO_GITHUB/NOMBRE-REPO.git
```

Solo debemos reemplazar con nuestros datos reales.
