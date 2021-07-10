# datos2021-tareas�🍿�
Repositorio creado para subir tareas y ejercicios realizados en la clase de datos1.


##### 1. Crear la tabla MOVIES.

#### Instrucciones: Realizar lo indicado en su base de datos Autonomous.  Por cada consulta solicitada en inciso 3, debe agregar la consulta y el resultado obtenido a este documento. 

![DDL](https://github.com/lsophiagr/datos2021-tareas/blob/main/images/foto1.png)

##### 2. Importar los datos con el archivo netfilx_titles.csv, desde SQL Developer.  (Tables, MOVIES, Import Data) 👀
Tablas importadas


##### 3. Realizar las consultas siguientes: 
1.    CANTIDAD DE PELICULAS AGREGADAS POR AÑO (ADDED_DATE)
2.    AÑOS CON MAS DE 10 PELICULAS AGREGADAS (ADDED_DATE)
3.    LISTADO DE AÑOS Y PELICULAS LIBERADAS (RELEASE_DATE) 
4.    NOMBRE Y AÑO (RELEASE_DATE) DE PELICULAS DE QUENTIN TARENTINO
5.    NOMBRE Y GENERO DE PELICULAS EN LAS QUE ACTUA SCARLETT JOHANSSON
6.    PELICULAS DE ZOMBIES 
7.    PELICULA MAS RECIENTE PUBLICADA DE BRAD PITT
8.    DURACION DE DARK


##### CANTIDAD DE PELICULAS AGREGADAS POR AÑO (ADDED_DATE) 🧞
select date_added,
count(show_id) 
from movies 
group by date_added;
![Query_1](https://github.com/lsophiagr/datos2021-tareas/blob/main/images/foto%202.png)



##### AÑOS CON MAS DE 10 PELICULAS AGREGADAS (ADDED_DATE)
select release_year, 
count(show_id) 
from movies 
group by release_year 
having count(show_id) > 10;

![Query_1](https://github.com/lsophiagr/datos2021-tareas/blob/main/images/foto%203.png)


##### LISTADO DE AÑOS Y PELICULAS LIBERADAS (RELEASE_DATE) 

select release_year, title 
from movies 
order by release_year desc;


![Query_1](https://github.com/lsophiagr/datos2021-tareas/blob/main/images/foto%204.png)


##### NOMBRE Y AÑO (RELEASE_DATE) DE PELICULAS DE QUENTIN TARENTINO👨‍🦰
select title, release_year 
from movies 
where director = 'Quentin Tarantino' 
order by release_year;




![Query_1](https://github.com/lsophiagr/datos2021-tareas/blob/main/images/foto%205.png)


##### NOMBRE Y GENERO DE PELICULAS EN LAS QUE ACTUA SCARLETT JOHANSSON👩‍
select title, listed_in 
from movies 
where castVal like '%Scarlett Johansson%'
order by release_year;




![Query_1](https://github.com/lsophiagr/datos2021-tareas/blob/main/images/foto%206.png)


##### PELICULAS DE ZOMBIES 🧟‍♀️🧟‍♀️🧟‍
select title 
from movies 
where descriptionVal 
like '%zombie%'
order by release_year;





![Query_1](https://github.com/lsophiagr/datos2021-tareas/blob/main/images/foto%207.png)


##### PELICULA MAS RECIENTE PUBLICADA DE BRAD PITT🧛
select title, release_year 
from movies 
where castVal like '%Brad Pitt%' and release_year = (
select max(release_year) 
from movies 
where castVal like '%Brad Pitt%');




![Query_1](https://github.com/lsophiagr/datos2021-tareas/blob/main/images/foto%208.png)


##### DURACION DE DARK ☠️☠️
select title, durationVal f
rom movies 
where title = 'Dark';



![Query_1](https://github.com/lsophiagr/datos2021-tareas/blob/main/images/foto%209.png)
