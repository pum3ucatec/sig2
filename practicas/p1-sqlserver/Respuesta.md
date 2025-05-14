1. Primero clonar el repositorio remoto

```
git clone https://github.com/pum3ucatec/sig2.git
```

2. Crear rama

```
git checkout -b MarisolHerrera/Practica1
```

3. Copiar lo esencial de la carpeta **ejemplos/e1-sqlserver**

4. Crear el archivo **Respuesta.md**

5. Crear el archivo **.env**

6. Iniciar el contenedor SQL Server

```
docker-compose up -d
```

![Consola](/sig2/practicas/p1-sqlserver/img/Iniciar_contenedor.png)

7. Ver contenedores en ejecución

```
docker ps
```

![Consola](/sig2/practicas/p1-sqlserver/img/Ver_contenedores.png)

8. Consultar bases de datos, cambiar los datos necesarios, como el nombre y contraseña

```
docker exec -it container_name /opt/mssql-tools18/bin/sqlcmd -S localhost -U SA -P "your_password" -C -d master -Q "SELECT name FROM sys.databases;"
```

#Ejemplo

```
 docker exec -it sqlserver_db /opt/mssql-tools18/bin/sqlcmd -S localhost -U SA -P "Marisol.2025" -C -d master -Q "SELECT name FROM sys.databases;"
```

![Consola](/sig2/practicas/p1-sqlserver/img/ConsultarBD.png)

9. Revisar los cambios a realizar

```
git status
```

10. Agregar todos los cambios

```
git add .
```

11. Comentar acerca de los cambios que se estan realizando

```
git commit -m "Primera practica de SIG 2"
```

12. Subir los commits a la rama actual del repositorio remoto

```
git push
```
