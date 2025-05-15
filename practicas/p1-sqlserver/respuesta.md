# Práctica 1: Configuración de SQL Server en Docker **(Windows 11)**

## Requisitos Previos
- Herramienta Docker instalado [**Dodcker**](https://www.docker.com/)
- Git instalado [**GIT**](https://git-scm.com/) 
- GitHub [**Github**](https://github.com/)

## 1. Configuración Inicial del Repositorio

1. Primero clonar el repositorio remoto

```
git clone https://github.com/pum3ucatec/sig2.git
cd sig2
```

2. Crear y cambiar a tu rama personal

```
git checkout -b MaideMamani/Practica1
```

## 2. Entorno de ejecución

- Archivos base

1. Copiar la carpeta **ejemplos/e1-sqlserver**

2. Crear archivo **respuesta.md** y **.env**

## 3. Configuración variables

1. Editar el archivo .env con:

```
SA_PASSWORD = "Maide@2025"
```

## 4. Despliegue del Contenedor SQL Server

1. Conexión y Operaciones en SQL Server

Conectarse al servidor, ejecución y consulta a la base de datos


```
docker compose up -d
```

![Consola](/practicas/p1-sqlserver/imagen/Docker_C.png)

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
git commit -m "Practica1 realizada"
```

4. Subir cambios

```
git push origin MaideMamani/Practica1
```


### Problemas durante la ejecución


