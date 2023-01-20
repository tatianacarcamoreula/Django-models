![Inove banner](/inove.jpg)
Inove Escuela de Código\
info@inove.com.ar\
Web: [Inove](http://inove.com.ar)

---
# Tarea: Django - Modelos y Administrador

Al realizar esta tarea pondremos en práctica los conocimientos adquiridos en clase.
Una vez finalizada, el alumno debe subir el enlace a su repositorio "forkeado" el foro de tarea correspondiente -NO SE ADMITE LA DEVOLUCIÓN POR OTRO CANAL SALVO SE ESPECIFIQUE LO CONTRARIO- 

Recuerde que no debe subir la base de datos al sistema, para ello se encuentra el archivo .gitignore que especifica los archivos y directorios omitidos.

---

### 1. Utilizar el proyecto de "Marvel" visto en clase.
Descargar el repositorio del material visto en clase, hacer que levante y configurarlo para que el mismo
pueda trabajar con una base de datos de tipo "Postgres".
Modifique las credenciales para el acceso en el archivo docker-compose.yml y haga que la aplicación pueda utilizarlas.

### 2. Realizar las migraciones del sistema.
Recuerde que para poder comenzar a utilizar el Django Admin, es necesario que el sistema se encuentre alineado con la base de datos. Para ello debemos realizar las migraciones de la aplicación y crear un nuevo superusuario.
Los comandos necesarios se encuentran detallados en el archivo README.md

### 3. Habilitar las entidades en models.py
Habilite la entidad creada en clase "Comic" que se encuentra comentada en el archivo models.py.

### 4. Personalice el administrador de Django.
Familiarícese con la aplicación, personalice el administrador de Django utilizando los atributos de admin.py.

### 5. Genere una nueva entidad en models.py 
Diseñe una nueva entidad en models.py, llamada "WishList" y agréguele los campos (columnas en la tabla resultante):
* id
* user (Este campo debe ser un Foreign Key relacionando con el modelo **User** que ofrece Django).
* comic (Este campo debe ser un Foreign Key relacionando con el Modelo **Comic**).
* favorite
* cart
* wished_qty
* bought_qty 

Debe basarse en el siguiente diseño de entidades:

![Entidades](/entidades.png)

Tip:
El atributo "comic" del modelo es un campo de tipo FK, para poder implementarlo utilizaremos:

```
comic = models.ForeignKey(
    Comic,
    verbose_name='Comic',
    on_delete=models.CASCADE,
    default=1,
    blank=True
)
```
Cuyos argumentos son:

* Comic --> El nombre de la clase (modelo) que hace referencia a la entidad "comic".
* on_delete=models.CASCADE --> Hace que al borrar un registro, se borren sus relacionados.
    - Links de Interés:
      - [Documentación de Django](https://docs.djangoproject.com/en/3.2/ref/models/fields/#arguments)
      - [Stack Overflow](https://stackoverflow.com/questions/38388423/what-does-on-delete-do-on-django-models)
* default --> Valor por defecto si no se le agrega ninguno.
* blank --> Permite que se inserte un registro con este campo vacío.

### 6. Nueva entidad en Django Admin.
Haga que la nueva entidad aparezca en el administrador de Django, recuerde realizar las migraciones previamente y lo trabajado en admin.py

---

## ¿Dudas?
Ante cualquier inquietud, debe referirse a los canales especificados para su trato en Inove.