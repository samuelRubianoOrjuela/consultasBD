# Taller Nro 2 Bases de datos 
---

### Consultas sobre una tabla
1. Lista el primer apellido de todos los empleados.

   ```sql
   SELECT apellido1 FROM empleado;

   +-----------+
   | apellido1 |
   +-----------+
   | Rivero    |
   | Salas     |
   | Rubio     |
   | Suárez    |
   | Loyola    |
   | Santana   |
   | Ruiz      |
   | Ruiz      |
   | Gómez     |
   | Flores    |
   | Herrera   |
   | Salas     |
   | Sáez      |
   +-----------+
   ```

---
2. Lista el primer apellido de los empleados eliminando los apellidos que estén repetidos.
   ```sql
   SELECT DISTINCT apellido1 FROM empleado;

   +-----------+
   | apellido1 |
   +-----------+
   | Rivero    |
   | Salas     |
   | Rubio     |
   | Suárez    |
   | Loyola    |
   | Santana   |
   | Ruiz      |
   | Gómez     |
   | Flores    |
   | Herrera   |
   | Sáez      |
   +-----------+
   ```

---
3. Lista todas las columnas de la tabla empleado.
   ```sql
   SELECT id, nif, nombre, apellido1, apellido2, id_departamento FROM empleado;

   +----+-----------+--------------+-----------+-----------+-----------------+
   | id | nif       | nombre       | apellido1 | apellido2 | id_departamento |
   +----+-----------+--------------+-----------+-----------+-----------------+
   |  1 | 32481596F | Aarón        | Rivero    | Gómez     |               1 |
   |  2 | Y5575632D | Adela        | Salas     | Díaz      |               2 |
   |  3 | R6970642B | Adolfo       | Rubio     | Flores    |               3 |
   |  4 | 77705545E | Adrián       | Suárez    | NULL      |               4 |
   |  5 | 17087203C | Marcos       | Loyola    | Méndez    |               5 |
   |  6 | 38382980M | María        | Santana   | Moreno    |               1 |
   |  7 | 80576669X | Pilar        | Ruiz      | NULL      |               2 |
   |  8 | 71651431Z | Pepe         | Ruiz      | Santana   |               3 |
   |  9 | 56399183D | Juan         | Gómez     | López     |               2 |
   | 10 | 46384486H | Diego        | Flores    | Salas     |               5 |
   | 11 | 67389283A | Marta        | Herrera   | Gil       |               1 |
   | 12 | 41234836R | Irene        | Salas     | Flores    |            NULL |
   | 13 | 82635162B | Juan Antonio | Sáez      | Guerrero  |            NULL |
   +----+-----------+--------------+-----------+-----------+-----------------+
   ```
---
4. Lista el nombre y los apellidos de todos los empleados.
   ```sql
   SELECT nombre, apellido1, apellido2 FROM empleado;

   +--------------+-----------+-----------+
   | nombre       | apellido1 | apellido2 |
   +--------------+-----------+-----------+
   | Aarón        | Rivero    | Gómez     |
   | Adela        | Salas     | Díaz      |
   | Adolfo       | Rubio     | Flores    |
   | Adrián       | Suárez    | NULL      |
   | Marcos       | Loyola    | Méndez    |
   | María        | Santana   | Moreno    |
   | Pilar        | Ruiz      | NULL      |
   | Pepe         | Ruiz      | Santana   |
   | Juan         | Gómez     | López     |
   | Diego        | Flores    | Salas     |
   | Marta        | Herrera   | Gil       |
   | Irene        | Salas     | Flores    |
   | Juan Antonio | Sáez      | Guerrero  |
   +--------------+-----------+-----------+
   ```

---
5. Lista el identificador de los departamentos de los empleados que aparecen en la tabla empleado.
   ```sql
   SELECT id_departamento FROM empleado;

   +-----------------+
   | id_departamento |
   +-----------------+
   |            NULL |
   |            NULL |
   |               1 |
   |               1 |
   |               1 |
   |               2 |
   |               2 |
   |               2 |
   |               3 |
   |               3 |
   |               4 |
   |               5 |
   |               5 |
   +-----------------+
   ```
---
6. Lista el identificador de los departamentos de los empleados que aparecen en la tabla empleado, eliminando los identificadores que aparecen repetidos.
   ```sql
   SELECT DISTINCT id_departamento FROM empleado;

   +-----------------+
   | id_departamento |
   +-----------------+
   |            NULL |
   |               1 |
   |               2 |
   |               3 |
   |               4 |
   |               5 |
   +-----------------+
   ```
---
7. Lista el nombre y apellidos de los empleados en una única columna.
   ```sql
   SELECT CONCAT(nombre, ' ', apellido1, ' ', apellido2) AS nombre_completo FROM empleado;

   +----------------------------+
   | nombre_completo            |
   +----------------------------+
   | Aarón Rivero Gómez         |
   | Adela Salas Díaz           |
   | Adolfo Rubio Flores        |
   | NULL                       |
   | Marcos Loyola Méndez       |
   | María Santana Moreno       |
   | NULL                       |
   | Pepe Ruiz Santana          |
   | Juan Gómez López           |
   | Diego Flores Salas         |
   | Marta Herrera Gil          |
   | Irene Salas Flores         |
   | Juan Antonio Sáez Guerrero |
   +----------------------------+
   ```

---
8. Lista el nombre y apellidos de los empleados en una única columna, convirtiendo todos los caracteres en mayúscula.
   ```sql
   SELECT UPPER(CONCAT(nombre, ' ', apellido1, ' ', apellido2)) AS nombre_completo FROM empleado;

   +----------------------------+
   | nombre_completo            |
   +----------------------------+
   | AARÓN RIVERO GÓMEZ         |
   | ADELA SALAS DÍAZ           |
   | ADOLFO RUBIO FLORES        |
   | NULL                       |
   | MARCOS LOYOLA MÉNDEZ       |
   | MARÍA SANTANA MORENO       |
   | NULL                       |
   | PEPE RUIZ SANTANA          |
   | JUAN GÓMEZ LÓPEZ           |
   | DIEGO FLORES SALAS         |
   | MARTA HERRERA GIL          |
   | IRENE SALAS FLORES         |
   | JUAN ANTONIO SÁEZ GUERRERO |
   +----------------------------+
   ```
---
9. Lista el nombre y apellidos de los empleados en una única columna, convirtiendo todos los caracteres en minúscula.
   ```sql
   SELECT LOWER(CONCAT(nombre, ' ', apellido1, ' ', apellido2)) AS nombre_completo FROM empleado;

   +----------------------------+
   | nombre_completo            |
   +----------------------------+
   | aarón rivero gómez         |
   | adela salas díaz           |
   | adolfo rubio flores        |
   | NULL                       |
   | marcos loyola méndez       |
   | maría santana moreno       |
   | NULL                       |
   | pepe ruiz santana          |
   | juan gómez lópez           |
   | diego flores salas         |
   | marta herrera gil          |
   | irene salas flores         |
   | juan antonio sáez guerrero |
   +----------------------------+
   ```


---
10. Lista el identificador de los empleados junto al nif, pero el nif deberá aparecer en dos columnas, una mostrará únicamente los dígitos del nif y la otra la letra.
   ```sql
   SELECT id, 
   SUBSTRING(nif, 1, LENGTH(nif)-1) AS nif_digitos, 
   RIGHT(nif, 1) AS nif_letra 
   FROM empleado;

   +----+-------------+-----------+
   | id | nif_digitos | nif_letra |
   +----+-------------+-----------+
   |  1 | 32481596    | F         |
   |  2 | Y5575632    | D         |
   |  3 | R6970642    | B         |
   |  4 | 77705545    | E         |
   |  5 | 17087203    | C         |
   |  6 | 38382980    | M         |
   |  7 | 80576669    | X         |
   |  8 | 71651431    | Z         |
   |  9 | 56399183    | D         |
   | 10 | 46384486    | H         |
   | 11 | 67389283    | A         |
   | 12 | 41234836    | R         |
   | 13 | 82635162    | B         |
   +----+-------------+-----------+
   ```


---
11. Lista el nombre de cada departamento y el valor del presupuesto actual del que dispone. Para calcular este dato tendrá que restar al valor del presupuesto inicial (columna presupuesto) los gastos que se han generado (columna gastos). Tenga en cuenta que en algunos casos pueden existir valores negativos. Utilice un alias apropiado para la nueva columna columna que está calculando.
   ```sql
   SELECT nombre,
	presupuesto-gastos AS presupuesto_actual
   FROM departamento;

   +------------------+--------------------+
   | nombre           | presupuesto_actual |
   +------------------+--------------------+
   | Desarrollo       |             114000 |
   | Sistemas         |             129000 |
   | Recursos Humanos |             255000 |
   | Contabilidad     |             107000 |
   | I+D              |              -5000 |
   | Proyectos        |                  0 |
   | Publicidad       |              -1000 |
   +------------------+--------------------+
   ```


---
12. Lista el nombre de los departamentos y el valor del presupuesto actual ordenado de forma ascendente.
   ```sql       
   SELECT nombre,
	presupuesto-gastos AS presupuesto_actual
   FROM departamento
   ORDER BY presupuesto_actual ASC;

   +------------------+--------------------+
   | nombre           | presupuesto_actual |
   +------------------+--------------------+
   | I+D              |              -5000 |
   | Publicidad       |              -1000 |
   | Proyectos        |                  0 |
   | Contabilidad     |             107000 |
   | Desarrollo       |             114000 |
   | Sistemas         |             129000 |
   | Recursos Humanos |             255000 |
   +------------------+--------------------+
   ```


---
13. Lista el nombre de todos los departamentos ordenados de forma ascendente.
   ```sql
   SELECT nombre
   FROM departamento
   ORDER BY nombre ASC;

   +------------------+
   | nombre           |
   +------------------+
   | Contabilidad     |
   | Desarrollo       |
   | I+D              |
   | Proyectos        |
   | Publicidad       |
   | Recursos Humanos |
   | Sistemas         |
   +------------------+
   ```


---
14. Lista el nombre de todos los departamentos ordenados de forma descendente.
   ```sql
   SELECT nombre
   FROM departamento
   ORDER BY nombre DESC;

   +------------------+
   | nombre           |
   +------------------+
   | Sistemas         |
   | Recursos Humanos |
   | Publicidad       |
   | Proyectos        |
   | I+D              |
   | Desarrollo       |
   | Contabilidad     |
   +------------------+
   ```
---
15. Lista los apellidos y el nombre de todos los empleados, ordenados de forma alfabética tendiendo en cuenta en primer lugar sus apellidos y luego su nombre.
   ```sql
   SELECT apellido1, apellido2, nombre
   FROM empleado
   ORDER BY apellido1 ASC;

   +-----------+-----------+--------------+
   | apellido1 | apellido2 | nombre       |
   +-----------+-----------+--------------+
   | Flores    | Salas     | Diego        |
   | Gómez     | López     | Juan         |
   | Herrera   | Gil       | Marta        |
   | Loyola    | Méndez    | Marcos       |
   | Rivero    | Gómez     | Aarón        |
   | Rubio     | Flores    | Adolfo       |
   | Ruiz      | NULL      | Pilar        |
   | Ruiz      | Santana   | Pepe         |
   | Sáez      | Guerrero  | Juan Antonio |
   | Salas     | Díaz      | Adela        |
   | Salas     | Flores    | Irene        |
   | Santana   | Moreno    | María        |
   | Suárez    | NULL      | Adrián       |
   +-----------+-----------+--------------+
   ```


---
16. Devuelve una lista con el nombre y el presupuesto, de los 3 departamentos que tienen mayor presupuesto.
   ```sql
   SELECT nombre, presupuesto
   FROM departamento
   ORDER BY presupuesto DESC
   LIMIT 3;

   +------------------+-------------+
   | nombre           | presupuesto |
   +------------------+-------------+
   | I+D              |      375000 |
   | Recursos Humanos |      280000 |
   | Sistemas         |      150000 |
   +------------------+-------------+
   ```

---
17. Devuelve una lista con el nombre y el presupuesto, de los 3 departamentos que tienen menor presupuesto.
   ```sql
   SELECT nombre, presupuesto
   FROM departamento
   ORDER BY presupuesto ASC
   LIMIT 3;

   +--------------+-------------+
   | nombre       | presupuesto |
   +--------------+-------------+
   | Proyectos    |           0 |
   | Publicidad   |           0 |
   | Contabilidad |      110000 |
   +--------------+-------------+
   ```

---
18. Devuelve una lista con el nombre y el gasto, de los 2 departamentos que tienen mayor gasto.
   ```sql
   SELECT nombre, gastos
   FROM departamento
   ORDER BY gastos ASC
   LIMIT 2;

   +------------+--------+
   | nombre     | gastos |
   +------------+--------+
   | Proyectos  |      0 |
   | Publicidad |   1000 |
   +------------+--------+
   ```
---
19. Devuelve una lista con el nombre y el gasto, de los 2 departamentos que tienen menor gasto.
   ```sql
   SELECT nombre, gastos
   FROM departamento
   ORDER BY gastos DESC
   LIMIT 2;

   +------------------+--------+
   | nombre           | gastos |
   +------------------+--------+
   | I+D              | 380000 |
   | Recursos Humanos |  25000 |
   +------------------+--------+
   ```
---
20. Devuelve una lista con 5 filas a partir de la tercera fila de la tabla empleado. La tercera fila se debe incluir en la respuesta. La respuesta debe incluir todas las columnas de la tabla empleado.
   ```sql
   SELECT id, nif, nombre, apellido1, apellido2, id_departamento
   FROM empleado
   LIMIT 5 OFFSET 2;

   +----+-----------+--------+-----------+-----------+-----------------+
   | id | nif       | nombre | apellido1 | apellido2 | id_departamento |
   +----+-----------+--------+-----------+-----------+-----------------+
   |  3 | R6970642B | Adolfo | Rubio     | Flores    |               3 |
   |  4 | 77705545E | Adrián | Suárez    | NULL      |               4 |
   |  5 | 17087203C | Marcos | Loyola    | Méndez    |               5 |
   |  6 | 38382980M | María  | Santana   | Moreno    |               1 |
   |  7 | 80576669X | Pilar  | Ruiz      | NULL      |               2 |
   +----+-----------+--------+-----------+-----------+-----------------+
   ```
---
21. Devuelve una lista con el nombre de los departamentos y el presupuesto, de aquellos que tienen un presupuesto mayor o igual a 150000 euros.
   ```sql
   SELECT nombre, presupuesto
   FROM departamento
   WHERE presupuesto >= 150000;

   +------------------+-------------+
   | nombre           | presupuesto |
   +------------------+-------------+
   | Sistemas         |      150000 |
   | Recursos Humanos |      280000 |
   | I+D              |      375000 |
   +------------------+-------------+
   ```
---
22. Devuelve una lista con el nombre de los departamentos y el gasto, de aquellos que tienen menos de 5000 euros de gastos.
   ```sql
   SELECT nombre, gastos
   FROM departamento
   WHERE gastos < 5000;

   +--------------+--------+
   | nombre       | gastos |
   +--------------+--------+
   | Contabilidad |   3000 |
   | Proyectos    |      0 |
   | Publicidad   |   1000 |
   +--------------+--------+
   ```
---
23. Devuelve una lista con el nombre de los departamentos y el presupuesto, de aquellos que tienen un presupuesto entre 100000 y 200000 euros. Sin utilizar el operador BETWEEN.
   ```sql
   SELECT nombre, presupuesto
   FROM departamento
   WHERE presupuesto >= 100000 AND presupuesto <= 200000;

   +--------------+-------------+
   | nombre       | presupuesto |
   +--------------+-------------+
   | Desarrollo   |      120000 |
   | Sistemas     |      150000 |
   | Contabilidad |      110000 |
   +--------------+-------------+
   ```
---
24. Devuelve una lista con el nombre de los departamentos que no tienen un presupuesto entre 100000 y 200000 euros. Sin utilizar el operador BETWEEN.
   ```sql
   SELECT nombre, presupuesto
   FROM departamento
   WHERE presupuesto < 100000 OR presupuesto > 200000;

   +------------------+-------------+
   | nombre           | presupuesto |
   +------------------+-------------+
   | Recursos Humanos |      280000 |
   | I+D              |      375000 |
   | Proyectos        |           0 |
   | Publicidad       |           0 |
   +------------------+-------------+
   ```
---
25. Devuelve una lista con el nombre de los departamentos que tienen un presupuesto entre 100000 y 200000 euros. Utilizando el operador BETWEEN.
   ```sql
   SELECT nombre, presupuesto
   FROM departamento
   WHERE presupuesto BETWEEN 100000 AND 200000;


   +--------------+-------------+
   | nombre       | presupuesto |
   +--------------+-------------+
   | Desarrollo   |      120000 |
   | Sistemas     |      150000 |
   | Contabilidad |      110000 |
   +--------------+-------------+
   ```
---
26. Devuelve una lista con el nombre de los departamentos que no tienen un presupuesto entre 100000 y 200000 euros. Utilizando el operador BETWEEN.
   ```sql
   SELECT nombre, presupuesto
   FROM departamento
   WHERE presupuesto NOT BETWEEN 100000 AND 200000;

   +------------------+-------------+
   | nombre           | presupuesto |
   +------------------+-------------+
   | Recursos Humanos |      280000 |
   | I+D              |      375000 |
   | Proyectos        |           0 |
   | Publicidad       |           0 |
   +------------------+-------------+
   ```
---
27. Devuelve una lista con el nombre de los departamentos, gastos y presupuesto, de aquellos departamentos donde los gastos sean mayores que el presupuesto del que disponen.
   ```sql
   SELECT nombre, gastos, presupuesto
   FROM departamento
   WHERE gastos > presupuesto;

   +------------+--------+-------------+
   | nombre     | gastos | presupuesto |
   +------------+--------+-------------+
   | I+D        | 380000 |      375000 |
   | Publicidad |   1000 |           0 |
   +------------+--------+-------------+
   ```
---
28. Devuelve una lista con el nombre de los departamentos, gastos y presupuesto, de aquellos departamentos donde los gastos sean menores que el presupuesto del que disponen.
   ```sql
   SELECT nombre, gastos, presupuesto
   FROM departamento
   WHERE gastos < presupuesto; 

   +------------------+--------+-------------+
   | nombre           | gastos | presupuesto |
   +------------------+--------+-------------+
   | Desarrollo       |   6000 |      120000 |
   | Sistemas         |  21000 |      150000 |
   | Recursos Humanos |  25000 |      280000 |
   | Contabilidad     |   3000 |      110000 |
   +------------------+--------+-------------+
   ```
---
29. Devuelve una lista con el nombre de los departamentos, gastos y presupuesto, de aquellos departamentos donde los gastos sean iguales al presupuesto del que disponen.
   ```sql
   SELECT nombre, gastos, presupuesto
   FROM departamento
   WHERE gastos = presupuesto;

   +-----------+--------+-------------+
   | nombre    | gastos | presupuesto |
   +-----------+--------+-------------+
   | Proyectos |      0 |           0 |
   +-----------+--------+-------------+
   ```
---
30. Lista todos los datos de los empleados cuyo segundo apellido sea NULL.
   ```sql
   SELECT id, nif, nombre, apellido1, apellido2, id_departamento
   FROM empleado
   WHERE apellido2 IS NULL;

   +----+-----------+--------+-----------+-----------+-----------------+
   | id | nif       | nombre | apellido1 | apellido2 | id_departamento |
   +----+-----------+--------+-----------+-----------+-----------------+
   |  4 | 77705545E | Adrián | Suárez    | NULL      |               4 |
   |  7 | 80576669X | Pilar  | Ruiz      | NULL      |               2 |
   +----+-----------+--------+-----------+-----------+-----------------+
   ```
---
31. Lista todos los datos de los empleados cuyo segundo apellido no sea NULL.
   ```sql
   SELECT id, nif, nombre, apellido1, apellido2, id_departamento
   FROM empleado
   WHERE apellido2 IS NOT NULL;

   +----+-----------+--------------+-----------+-----------+-----------------+
   | id | nif       | nombre       | apellido1 | apellido2 | id_departamento |
   +----+-----------+--------------+-----------+-----------+-----------------+
   |  1 | 32481596F | Aarón        | Rivero    | Gómez     |               1 |
   |  2 | Y5575632D | Adela        | Salas     | Díaz      |               2 |
   |  3 | R6970642B | Adolfo       | Rubio     | Flores    |               3 |
   |  5 | 17087203C | Marcos       | Loyola    | Méndez    |               5 |
   |  6 | 38382980M | María        | Santana   | Moreno    |               1 |
   |  8 | 71651431Z | Pepe         | Ruiz      | Santana   |               3 |
   |  9 | 56399183D | Juan         | Gómez     | López     |               2 |
   | 10 | 46384486H | Diego        | Flores    | Salas     |               5 |
   | 11 | 67389283A | Marta        | Herrera   | Gil       |               1 |
   | 12 | 41234836R | Irene        | Salas     | Flores    |            NULL |
   | 13 | 82635162B | Juan Antonio | Sáez      | Guerrero  |            NULL |
   +----+-----------+--------------+-----------+-----------+-----------------+
   ```
---
32. Lista todos los datos de los empleados cuyo segundo apellido sea López.
   ```sql
   SELECT id, nif, nombre, apellido1, apellido2, id_departamento
   FROM empleado
   WHERE apellido2 = 'López';

   +----+-----------+--------+-----------+-----------+-----------------+
   | id | nif       | nombre | apellido1 | apellido2 | id_departamento |
   +----+-----------+--------+-----------+-----------+-----------------+
   |  9 | 56399183D | Juan   | Gómez     | López     |               2 |
   +----+-----------+--------+-----------+-----------+-----------------+
   ```
---
33. Lista todos los datos de los empleados cuyo segundo apellido sea Díaz o Moreno. Sin utilizar el operador IN.
   ```sql
   SELECT id, nif, nombre, apellido1, apellido2, id_departamento
   FROM empleado
   WHERE apellido2 = 'Díaz' OR apellido2 = 'Moreno';

   +----+-----------+--------+-----------+-----------+-----------------+
   | id | nif       | nombre | apellido1 | apellido2 | id_departamento |
   +----+-----------+--------+-----------+-----------+-----------------+
   |  2 | Y5575632D | Adela  | Salas     | Díaz      |               2 |
   |  6 | 38382980M | María  | Santana   | Moreno    |               1 |
   +----+-----------+--------+-----------+-----------+-----------------+
   ```
---
34. Lista todos los datos de los empleados cuyo segundo apellido sea Díaz o Moreno. Utilizando el operador IN.
   ```sql   
   SELECT id, nif, nombre, apellido1, apellido2, id_departamento
   FROM empleado
   WHERE apellido2 IN ('Díaz', 'Moreno');

   +----+-----------+--------+-----------+-----------+-----------------+
   | id | nif       | nombre | apellido1 | apellido2 | id_departamento |
   +----+-----------+--------+-----------+-----------+-----------------+
   |  2 | Y5575632D | Adela  | Salas     | Díaz      |               2 |
   |  6 | 38382980M | María  | Santana   | Moreno    |               1 |
   +----+-----------+--------+-----------+-----------+-----------------+
   ```
---
35. Lista los nombres, apellidos y nif de los empleados que trabajan en el departamento 3.
   ```sql
   SELECT nombre, apellido1, apellido2, nif
   FROM empleado
   WHERE id_departamento = 3;

   +--------+-----------+-----------+-----------+
   | nombre | apellido1 | apellido2 | nif       |
   +--------+-----------+-----------+-----------+
   | Adolfo | Rubio     | Flores    | R6970642B |
   | Pepe   | Ruiz      | Santana   | 71651431Z |
   +--------+-----------+-----------+-----------+
   ```
---
36. Lista los nombres, apellidos y nif de los empleados que trabajan en los departamentos 2, 4 o 5.   
   ```sql
   SELECT nombre, apellido1, apellido2, nif
   FROM empleado
   WHERE id_departamento IN (2, 4, 5);

   +--------+-----------+-----------+-----------+
   | nombre | apellido1 | apellido2 | nif       |
   +--------+-----------+-----------+-----------+
   | Adela  | Salas     | Díaz      | Y5575632D |
   | Pilar  | Ruiz      | NULL      | 80576669X |
   | Juan   | Gómez     | López     | 56399183D |
   | Adrián | Suárez    | NULL      | 77705545E |
   | Marcos | Loyola    | Méndez    | 17087203C |
   | Diego  | Flores    | Salas     | 46384486H |
   +--------+-----------+-----------+-----------+
   ```
---

### Consultas multitabla (Composición interna)

Resuelva todas las consultas utilizando la sintaxis de SQL1 y SQL2.

---
1. Devuelve un listado con los empleados y los datos de los departamentos donde trabaja cada uno.
   ```sql
   SELECT e.id, e.nif, e.nombre, e.apellido1, e.apellido2, d.id AS id_departamento, d.nombre AS nombre_departamento, d.presupuesto, d.gastos
   FROM empleado e, departamento d
   WHERE e.id = d.id;

   +----+-----------+--------+-----------+-----------+-----------------+---------------------+-------------+--------+
   | id | nif       | nombre | apellido1 | apellido2 | id_departamento | nombre_departamento | presupuesto | gastos |
   +----+-----------+--------+-----------+-----------+-----------------+---------------------+-------------+--------+
   |  1 | 32481596F | Aarón  | Rivero    | Gómez     |               1 | Desarrollo          |      120000 |   6000 |
   |  2 | Y5575632D | Adela  | Salas     | Díaz      |               2 | Sistemas            |      150000 |  21000 |
   |  3 | R6970642B | Adolfo | Rubio     | Flores    |               3 | Recursos Humanos    |      280000 |  25000 |
   |  4 | 77705545E | Adrián | Suárez    | NULL      |               4 | Contabilidad        |      110000 |   3000 |
   |  5 | 17087203C | Marcos | Loyola    | Méndez    |               5 | I+D                 |      375000 | 380000 |
   |  6 | 38382980M | María  | Santana   | Moreno    |               6 | Proyectos           |           0 |      0 |
   |  7 | 80576669X | Pilar  | Ruiz      | NULL      |               7 | Publicidad          |           0 |   1000 |
   +----+-----------+--------+-----------+-----------+-----------------+---------------------+-------------+--------+
   ```
---
2. Devuelve un listado con los empleados y los datos de los departamentos donde trabaja cada uno. Ordena el resultado, en primer lugar por el nombre del departamento (en orden alfabético) y en segundo lugar por los apellidos y el nombre de los empleados.
   ```sql
   SELECT d.nombre AS nombre_departamento, e.apellido1, e.apellido2, e.nombre
   FROM empleado e, departamento d
   WHERE e.id = d.id;

   +---------------------+-----------+-----------+--------+
   | nombre_departamento | apellido1 | apellido2 | nombre |
   +---------------------+-----------+-----------+--------+
   | Desarrollo          | Rivero    | Gómez     | Aarón  |
   | Sistemas            | Salas     | Díaz      | Adela  |
   | Recursos Humanos    | Rubio     | Flores    | Adolfo |
   | Contabilidad        | Suárez    | NULL      | Adrián |
   | I+D                 | Loyola    | Méndez    | Marcos |
   | Proyectos           | Santana   | Moreno    | María  |
   | Publicidad          | Ruiz      | NULL      | Pilar  |
   +---------------------+-----------+-----------+--------+
   ```
---
3. Devuelve un listado con el identificador y el nombre del departamento, solamente de aquellos departamentos que tienen empleados.
   ```sql
   SELECT d.id AS id_departamento, d.nombre AS nombre_departamento
   FROM departamento d
   INNER JOIN empleado e ON d.id = e.id_departamento
   GROUP BY id_departamento, nombre_departamento;

   +-----------------+---------------------+
   | id_departamento | nombre_departamento |
   +-----------------+---------------------+
   |               1 | Desarrollo          |
   |               2 | Sistemas            |
   |               3 | Recursos Humanos    |
   |               4 | Contabilidad        |
   |               5 | I+D                 |
   +-----------------+---------------------+
   ```
---
4. Devuelve un listado con el identificador, el nombre del departamento y el valor del presupuesto actual del que dispone, solamente de aquellos
   departamentos que tienen empleados. El valor del presupuesto actual lo puede calcular restando al valor del presupuesto inicial
   (columna presupuesto) el valor de los gastos que ha generado
   (columna gastos).
   ```sql
   SELECT d.id AS id_departamento, d.nombre AS nombre_departamento,
   d.presupuesto - d.gastos AS presupuesto_actual
   FROM departamento d
   INNER JOIN empleado e ON d.id = e.id_departamento
   GROUP BY id_departamento, nombre_departamento;

   +-----------------+---------------------+--------------------+
   | id_departamento | nombre_departamento | presupuesto_actual |
   +-----------------+---------------------+--------------------+
   |               1 | Desarrollo          |             114000 |
   |               2 | Sistemas            |             129000 |
   |               3 | Recursos Humanos    |             255000 |
   |               4 | Contabilidad        |             107000 |
   |               5 | I+D                 |              -5000 |
   +-----------------+---------------------+--------------------+
   ```
---
5. Devuelve el nombre del departamento donde trabaja el empleado que tiene el nif 38382980M.
   ```sql
   SELECT d.nombre AS nombre_departamento
   FROM departamento d
   INNER JOIN empleado e ON d.id = e.id_departamento
   WHERE e.nif = '38382980M';

   +---------------------+
   | nombre_departamento |
   +---------------------+
   | Desarrollo          |
   +---------------------+
   ```
---

6. Devuelve el nombre del departamento donde trabaja el empleado Pepe Ruiz Santana.
   ```sql
   SELECT d.nombre AS nombre_departamento
   FROM departamento d
   INNER JOIN empleado e ON d.id = e.id_departamento
   WHERE e.nombre = 'Pepe' AND e.apellido1 = 'Ruiz' AND e.apellido2 = 'Santana';

   +---------------------+
   | nombre_departamento |
   +---------------------+
   | Recursos Humanos    |
   +---------------------+
   ```
---
7. Devuelve un listado con los datos de los empleados que trabajan en el departamento de I+D. Ordena el resultado alfabéticamente.
   ```sql
   SELECT e.id, e.nif, e.nombre, e.apellido1, e.apellido2, e.id_departamento
   FROM departamento d
   INNER JOIN empleado e ON d.id = e.id_departamento
   WHERE e.id_departamento = 5
   ORDER BY e.nombre ASC;

   +----+-----------+--------+-----------+-----------+-----------------+
   | id | nif       | nombre | apellido1 | apellido2 | id_departamento |
   +----+-----------+--------+-----------+-----------+-----------------+
   | 10 | 46384486H | Diego  | Flores    | Salas     |               5 |
   |  5 | 17087203C | Marcos | Loyola    | Méndez    |               5 |
   +----+-----------+--------+-----------+-----------+-----------------+
   ```
---
8. Devuelve un listado con los datos de los empleados que trabajan en el departamento de Sistemas, Contabilidad o I+D. Ordena el resultado
   alfabéticamente.
   ```sql
   SELECT e.id, e.nif, e.nombre, e.apellido1, e.apellido2, e.id_departamento
   FROM departamento d
   INNER JOIN empleado e ON d.id = e.id_departamento
   WHERE e.id_departamento = 2 OR e.id_departamento = 4 OR e.id_departamento = 5 
   ORDER BY e.nombre ASC;

   +----+-----------+--------+-----------+-----------+-----------------+
   | id | nif       | nombre | apellido1 | apellido2 | id_departamento |
   +----+-----------+--------+-----------+-----------+-----------------+
   |  2 | Y5575632D | Adela  | Salas     | Díaz      |               2 |
   |  4 | 77705545E | Adrián | Suárez    | NULL      |               4 |
   | 10 | 46384486H | Diego  | Flores    | Salas     |               5 |
   |  9 | 56399183D | Juan   | Gómez     | López     |               2 |
   |  5 | 17087203C | Marcos | Loyola    | Méndez    |               5 |
   |  7 | 80576669X | Pilar  | Ruiz      | NULL      |               2 |
   +----+-----------+--------+-----------+-----------+-----------------+
   ```
---
9. Devuelve una lista con el nombre de los empleados que tienen los
   departamentos que no tienen un presupuesto entre 100000 y 200000 euros.
   ```sql
   SELECT e.nombre
   FROM empleado e
   INNER JOIN departamento d ON d.id = e.id_departamento
   WHERE d.presupuesto NOT BETWEEN 100000 AND 200000;

   +--------+
   | nombre |
   +--------+
   | Adolfo |
   | Pepe   |
   | Marcos |
   | Diego  |
   +--------+
   ```
---
10. Devuelve un listado con el nombre de los departamentos donde existe algún empleado cuyo segundo apellido sea NULL. Tenga en cuenta que no debe mostrar nombres de departamentos que estén repetidos.
   ```sql
   SELECT DISTINCT d.nombre AS nombre_departamento
   FROM departamento d
   INNER JOIN empleado e ON d.id = e.id_departamento
   WHERE e.apellido2 IS NULL;

   +---------------------+
   | nombre_departamento |
   +---------------------+
   | Contabilidad        |
   | Sistemas            |
   +---------------------+
   ```
---

### Consultas multitabla (Composición externa)
Resuelva todas las consultas utilizando las cláusulas LEFT JOIN y RIGHT JOIN.

---
1. Devuelve un listado con todos los empleados junto con los datos de los departamentos donde trabajan. Este listado también debe incluir los empleados que no tienen ningún departamento asociado.
   ```sql
   SELECT e.id, e.nif, e.nombre, e.apellido1, e.apellido2, e.id_departamento,
   d.nombre AS nombre_departamento, d.presupuesto, d.gastos
   FROM empleado e
   LEFT JOIN departamento d ON e.id_departamento = d.id;

   +----+-----------+--------------+-----------+-----------+-----------------+---------------------+-------------+--------+
   | id | nif       | nombre       | apellido1 | apellido2 | id_departamento | nombre_departamento | presupuesto | gastos |
   +----+-----------+--------------+-----------+-----------+-----------------+---------------------+-------------+--------+
   |  1 | 32481596F | Aarón        | Rivero    | Gómez     |               1 | Desarrollo          |      120000 |   6000 |
   |  2 | Y5575632D | Adela        | Salas     | Díaz      |               2 | Sistemas            |      150000 |  21000 |
   |  3 | R6970642B | Adolfo       | Rubio     | Flores    |               3 | Recursos Humanos    |      280000 |  25000 |
   |  4 | 77705545E | Adrián       | Suárez    | NULL      |               4 | Contabilidad        |      110000 |   3000 |
   |  5 | 17087203C | Marcos       | Loyola    | Méndez    |               5 | I+D                 |      375000 | 380000 |
   |  6 | 38382980M | María        | Santana   | Moreno    |               1 | Desarrollo          |      120000 |   6000 |
   |  7 | 80576669X | Pilar        | Ruiz      | NULL      |               2 | Sistemas            |      150000 |  21000 |
   |  8 | 71651431Z | Pepe         | Ruiz      | Santana   |               3 | Recursos Humanos    |      280000 |  25000 |
   |  9 | 56399183D | Juan         | Gómez     | López     |               2 | Sistemas            |      150000 |  21000 |
   | 10 | 46384486H | Diego        | Flores    | Salas     |               5 | I+D                 |      375000 | 380000 |
   | 11 | 67389283A | Marta        | Herrera   | Gil       |               1 | Desarrollo          |      120000 |   6000 |
   | 12 | 41234836R | Irene        | Salas     | Flores    |            NULL | NULL                |        NULL |   NULL |
   | 13 | 82635162B | Juan Antonio | Sáez      | Guerrero  |            NULL | NULL                |        NULL |   NULL |
   +----+-----------+--------------+-----------+-----------+-----------------+---------------------+-------------+--------+
   ```
---
2. Devuelve un listado donde sólo aparezcan aquellos empleados que no tienen ningún departamento asociado.
   ```sql
   SELECT e.id, e.nif, e.nombre, e.apellido1, e.apellido2, e.id_departamento
   FROM empleado e
   LEFT JOIN departamento d ON e.id_departamento = d.id
   WHERE e.id_departamento IS NULL;

   +----+-----------+--------------+-----------+-----------+-----------------+
   | id | nif       | nombre       | apellido1 | apellido2 | id_departamento |
   +----+-----------+--------------+-----------+-----------+-----------------+
   | 12 | 41234836R | Irene        | Salas     | Flores    |            NULL |
   | 13 | 82635162B | Juan Antonio | Sáez      | Guerrero  |            NULL |
   +----+-----------+--------------+-----------+-----------+-----------------+
   ```
---
3. Devuelve un listado donde sólo aparezcan aquellos departamentos que no tienen ningún empleado asociado.
   ```sql
   SELECT d.id, d.nombre, d.presupuesto
   FROM departamento d
   LEFT JOIN empleado e ON d.id = e.id_departamento
   WHERE e.id_departamento IS NULL;

   +----+------------+-------------+
   | id | nombre     | presupuesto |
   +----+------------+-------------+
   |  6 | Proyectos  |           0 |
   |  7 | Publicidad |           0 |
   +----+------------+-------------+
   ```
---
4. Devuelve un listado con todos los empleados junto con los datos de los departamentos donde trabajan. El listado debe incluir los empleados que no tienen ningún departamento asociado y los departamentos que no tienen ningún empleado asociado. Ordene el listado alfabéticamente por el nombre del departamento.
   ```sql
   SELECT e.*, d.nombre AS nombre_departamento
   FROM empleado e
   LEFT JOIN departamento d ON e.id_departamento = d.id
   UNION
   SELECT e.*, 'Sin departamento' AS nombre_departamento
   FROM empleado e
   WHERE e.id_departamento IS NULL
   UNION
   SELECT NULL AS id, NULL AS nif, NULL AS nombre, NULL AS apellido1, NULL AS apellido2, d.id AS id_departamento, d.nombre AS nombre_departamento
   FROM departamento d
   WHERE NOT EXISTS (SELECT 1 FROM empleado WHERE id_departamento = d.id)
   ORDER BY nombre_departamento;

   +------+-----------+--------------+-----------+-----------+-----------------+---------------------+
   | id   | nif       | nombre       | apellido1 | apellido2 | id_departamento | nombre_departamento |
   +------+-----------+--------------+-----------+-----------+-----------------+---------------------+
   |   12 | 41234836R | Irene        | Salas     | Flores    |            NULL | NULL                |
   |   13 | 82635162B | Juan Antonio | Sáez      | Guerrero  |            NULL | NULL                |
   |    4 | 77705545E | Adrián       | Suárez    | NULL      |               4 | Contabilidad        |
   |    1 | 32481596F | Aarón        | Rivero    | Gómez     |               1 | Desarrollo          |
   |    6 | 38382980M | María        | Santana   | Moreno    |               1 | Desarrollo          |
   |   11 | 67389283A | Marta        | Herrera   | Gil       |               1 | Desarrollo          |
   |    5 | 17087203C | Marcos       | Loyola    | Méndez    |               5 | I+D                 |
   |   10 | 46384486H | Diego        | Flores    | Salas     |               5 | I+D                 |
   | NULL | NULL      | NULL         | NULL      | NULL      |               6 | Proyectos           |
   | NULL | NULL      | NULL         | NULL      | NULL      |               7 | Publicidad          |
   |    3 | R6970642B | Adolfo       | Rubio     | Flores    |               3 | Recursos Humanos    |
   |    8 | 71651431Z | Pepe         | Ruiz      | Santana   |               3 | Recursos Humanos    |
   |   12 | 41234836R | Irene        | Salas     | Flores    |            NULL | Sin departamento    |
   |   13 | 82635162B | Juan Antonio | Sáez      | Guerrero  |            NULL | Sin departamento    |
   |    2 | Y5575632D | Adela        | Salas     | Díaz      |               2 | Sistemas            |
   |    7 | 80576669X | Pilar        | Ruiz      | NULL      |               2 | Sistemas            |
   |    9 | 56399183D | Juan         | Gómez     | López     |               2 | Sistemas            |
   +------+-----------+--------------+-----------+-----------+-----------------+---------------------+
   ```
---
5. Devuelve un listado con los empleados que no tienen ningún departamento asociado y los departamentos que no tienen ningún empleado asociado. Ordene el listado alfabéticamente por el nombre del departamento.
   ```sql
   SELECT 'Empleado' AS tipo, e.id AS id_empleado, e.nif, e.nombre AS nombre_empleado, e.apellido1, e.apellido2, e.id_departamento AS id_departamento_empleado, NULL AS id_departamento, NULL AS nombre_departamento,NULL AS presupuesto
   FROM empleado e
   LEFT JOIN departamento d ON e.id_departamento = d.id
   WHERE e.id_departamento IS NULL
   UNION
   SELECT 'Departamento' AS tipo, NULL AS id_empleado, NULL AS nif, NULL AS nombre_empleado, NULL AS apellido1, NULL AS apellido2, NULL AS id_departamento_empleado, d.id AS id_departamento, d.nombre AS nombre_departamento, d.presupuesto
   FROM departamento d
   LEFT JOIN empleado e ON d.id = e.id_departamento
   WHERE e.id IS NULL
   ORDER BY nombre_departamento;

   +--------------+-------------+-----------+-----------------+-----------+-----------+--------------------------+-----------------+---------------------+-------------+
   | tipo         | id_empleado | nif       | nombre_empleado | apellido1 | apellido2 | id_departamento_empleado | id_departamento | nombre_departamento | presupuesto |
   +--------------+-------------+-----------+-----------------+-----------+-----------+--------------------------+-----------------+---------------------+-------------+
   | Empleado     |          12 | 41234836R | Irene           | Salas     | Flores    |                     NULL |            NULL | NULL                |        NULL |
   | Empleado     |          13 | 82635162B | Juan Antonio    | Sáez      | Guerrero  |                     NULL |            NULL | NULL                |        NULL |
   | Departamento |        NULL | NULL      | NULL            | NULL      | NULL      |                     NULL |               6 | Proyectos           |           0 |
   | Departamento |        NULL | NULL      | NULL            | NULL      | NULL      |                     NULL |               7 | Publicidad          |           0 |
   +--------------+-------------+-----------+-----------------+-----------+-----------+--------------------------+-----------------+---------------------+-------------+
   ```
---

### Consultas resumen
---

1. Calcula la suma del presupuesto de todos los departamentos.
   ```sql
   SELECT SUM(presupuesto) AS presupuesto_total
   FROM departamento;

   +-------------------+
   | presupuesto_total |
   +-------------------+
   |           1035000 |
   +-------------------+
   ```
---
2. Calcula la media del presupuesto de todos los departamentos.
   ```sql
   SELECT SUM(presupuesto) / COUNT(id) AS media_presupuesto
   FROM departamento;

   +--------------------+
   | media_presupuesto  |
   +--------------------+
   | 147857.14285714287 |
   +--------------------+
   ```
---
3. Calcula el valor mínimo del presupuesto de todos los departamentos.
   ```sql
   SELECT MIN(presupuesto) AS presupuesto_minimo
   FROM departamento;

   +--------------------+
   | presupuesto_minimo |
   +--------------------+
   |                  0 |
   +--------------------+
   ```
---
4. Calcula el nombre del departamento y el presupuesto que tiene asignado, del departamento con menor presupuesto.
   ```sql
   SELECT nombre, presupuesto
   FROM departamento
   ORDER BY presupuesto
   LIMIT 1;

   +-----------+-------------+
   | nombre    | presupuesto |
   +-----------+-------------+
   | Proyectos |           0 |
   +-----------+-------------+
   ```
---
5. Calcula el valor máximo del presupuesto de todos los departamentos.
   ```sql
   SELECT MAX(presupuesto) AS presupuesto_minimo
   FROM departamento;

   +--------------------+
   | presupuesto_minimo |
   +--------------------+
   |             375000 |
   +--------------------+
   ```
---
6. Calcula el nombre del departamento y el presupuesto que tiene asignado, del departamento con mayor presupuesto.
   ```sql
   SELECT nombre, presupuesto
   FROM departamento
   ORDER BY presupuesto DESC
   LIMIT 1;

   +--------+-------------+
   | nombre | presupuesto |
   +--------+-------------+
   | I+D    |      375000 |
   +--------+-------------+
   ```
---
7. Calcula el número total de empleados que hay en la tabla empleado.
   ```sql
   SELECT COUNT(id) AS total_empleados
   FROM empleado;

   +-----------------+
   | total_empleados |
   +-----------------+
   |              13 |
   +-----------------+
   ```
---
8. Calcula el número de empleados que no tienen NULL en su segundo apellido.
   ```sql
   SELECT COUNT(id) AS total_empleados
   FROM empleado
   WHERE apellido2 IS NOT NULL;

   +-----------------+
   | total_empleados |
   +-----------------+
   |              11 |
   +-----------------+
   ```
---
9. Calcula el número de empleados que hay en cada departamento. Tienes que devolver dos columnas, una con el nombre del departamento y otra con el número de empleados que tiene asignados.
   ```sql
   SELECT d.nombre AS nombre_departamento, COUNT(e.id) AS numero_empleados
   FROM departamento d
   LEFT JOIN empleado e ON d.id = e.id_departamento
   GROUP BY d.nombre;

   +---------------------+------------------+
   | nombre_departamento | numero_empleados |
   +---------------------+------------------+
   | Desarrollo          |                3 |
   | Sistemas            |                3 |
   | Recursos Humanos    |                2 |
   | Contabilidad        |                1 |
   | I+D                 |                2 |
   | Proyectos           |                0 |
   | Publicidad          |                0 |
   +---------------------+------------------+
   ```
---
10. Calcula el nombre de los departamentos que tienen más de 2 empleados. El resultado debe tener dos columnas, una con el nombre del departamento y otra con el número de empleados que tiene asignados.
   ```sql
   SELECT d.nombre AS nombre_departamento, COUNT(e.id) AS numero_empleados
   FROM departamento d
   LEFT JOIN empleado e ON d.id = e.id_departamento
   GROUP BY d.nombre
   HAVING COUNT(e.id) > 2;

   +---------------------+------------------+
   | nombre_departamento | numero_empleados |
   +---------------------+------------------+
   | Desarrollo          |                3 |
   | Sistemas            |                3 |
   +---------------------+------------------+
   ```
---
11. Calcula el número de empleados que trabajan en cada uno de los departamentos. El resultado de esta consulta también tiene que incluir aquellos departamentos que no tienen ningún empleado asociado.
   ```sql
   SELECT d.nombre AS nombre_departamento, COUNT(e.id) AS numero_empleados
   FROM departamento d
   LEFT JOIN empleado e ON d.id = e.id_departamento
   GROUP BY d.nombre;

   +---------------------+------------------+
   | nombre_departamento | numero_empleados |
   +---------------------+------------------+
   | Desarrollo          |                3 |
   | Sistemas            |                3 |
   | Recursos Humanos    |                2 |
   | Contabilidad        |                1 |
   | I+D                 |                2 |
   | Proyectos           |                0 |
   | Publicidad          |                0 |
   +---------------------+------------------+
   ```
---
12. Calcula el número de empleados que trabajan en cada unos de los departamentos que tienen un presupuesto mayor a 200000 euros.
   ```sql
   SELECT d.nombre AS nombre_departamento, COUNT(e.id) AS numero_empleados
   FROM departamento d
   LEFT JOIN empleado e ON d.id = e.id_departamento
   WHERE d.presupuesto > 200000
   GROUP BY d.nombre;

   +---------------------+------------------+
   | nombre_departamento | numero_empleados |
   +---------------------+------------------+
   | Recursos Humanos    |                2 |
   | I+D                 |                2 |
   +---------------------+------------------+
   ```
---

### Subconsultas

**Con operadores básicos de comparación**
---

1. Devuelve un listado con todos los empleados que tiene el departamento de Sistemas. (Sin utilizar INNER JOIN).
   ```sql
   SELECT id, nif, nombre, apellido1, apellido2, id_departamento
   FROM empleado
   WHERE id_departamento = (SELECT id FROM departamento WHERE nombre = 'Sistemas');

   +----+-----------+--------+-----------+-----------+-----------------+
   | id | nif       | nombre | apellido1 | apellido2 | id_departamento |
   +----+-----------+--------+-----------+-----------+-----------------+
   |  2 | Y5575632D | Adela  | Salas     | Díaz      |               2 |
   |  7 | 80576669X | Pilar  | Ruiz      | NULL      |               2 |
   |  9 | 56399183D | Juan   | Gómez     | López     |               2 |
   +----+-----------+--------+-----------+-----------+-----------------+
   ```
---
2. Devuelve el nombre del departamento con mayor presupuesto y la cantidad que tiene asignada.
   ```sql
   SELECT nombre, presupuesto
   FROM departamento
   WHERE presupuesto = (SELECT presupuesto FROM departamento ORDER BY presupuesto DESC LIMIT 1);
   
   +--------+-------------+
   | nombre | presupuesto |
   +--------+-------------+
   | I+D    |      375000 |
   +--------+-------------+
   ```
---
3. Devuelve el nombre del departamento con menor presupuesto y la cantidad que tiene asignada.
   ```sql
   SELECT nombre, presupuesto
   FROM departamento
   WHERE presupuesto = (SELECT presupuesto FROM departamento ORDER BY presupuesto ASC LIMIT 1)
   LIMIT 1;

   +-----------+-------------+
   | nombre    | presupuesto |
   +-----------+-------------+
   | Proyectos |           0 |
   +-----------+-------------+
   ```
---
**Subconsultas con ALL y ANY**

4. Devuelve el nombre del departamento con mayor presupuesto y la cantidad que tiene asignada. Sin hacer uso de MAX, ORDER BY ni LIMIT.
   ```sql
   SELECT nombre, presupuesto
   FROM departamento
   WHERE presupuesto >= ALL (SELECT presupuesto FROM departamento);

   +--------+-------------+
   | nombre | presupuesto |
   +--------+-------------+
   | I+D    |      375000 |
   +--------+-------------+
   ```
---
5. Devuelve el nombre del departamento con menor presupuesto y la cantidad que tiene asignada. Sin hacer uso de MIN, ORDER BY ni LIMIT.
   ```sql
   SELECT nombre, presupuesto
   FROM departamento
   WHERE presupuesto <= ALL (SELECT presupuesto FROM departamento)
   LIMIT 1;

   +-----------+-------------+
   | nombre    | presupuesto |
   +-----------+-------------+
   | Proyectos |           0 |
   +-----------+-------------+
   ```
---
6. Devuelve los nombres de los departamentos que tienen empleados asociados. (Utilizando ALL o ANY).
   ```sql
   SELECT nombre
   FROM departamento
   WHERE id = ANY (
      SELECT id_departamento
      FROM empleado
   );

   +------------------+
   | nombre           |
   +------------------+
   | Desarrollo       |
   | Sistemas         |
   | Recursos Humanos |
   | Contabilidad     |
   | I+D              |
   +------------------+
   ```
---
7. Devuelve los nombres de los departamentos que no tienen empleados asociados. (Utilizando ALL o ANY).
   ```sql
   SELECT nombre
   FROM departamento
   WHERE id <> ANY (
      SELECT id_departamento
      FROM empleado
   );

   +------------+
   | nombre     |
   +------------+
   | Proyectos  |
   | Publicidad |
   +------------+
   ```
---
**Subconsultas con IN y NOT IN**

8. Devuelve los nombres de los departamentos que tienen empleados asociados. (Utilizando IN o NOT IN).
   ```sql
   SELECT nombre
   FROM departamento
   WHERE id IN (
      SELECT id_departamento
      FROM empleado
   );

   +------------------+
   | nombre           |
   +------------------+
   | Desarrollo       |
   | Sistemas         |
   | Recursos Humanos |
   | Contabilidad     |
   | I+D              |
   +------------------+
   ```
---
9. Devuelve los nombres de los departamentos que no tienen empleados asociados. (Utilizando IN o NOT IN).
   ```sql
   SELECT nombre
   FROM departamento
   WHERE id NOT IN (
      SELECT id_departamento
      FROM empleado
   );

   +------------+
   | nombre     |
   +------------+
   | Proyectos  |
   | Publicidad |
   +------------+
   ```
---
**Subconsultas con EXISTS y NOT EXISTS**

10. Devuelve los nombres de los departamentos que tienen empleados asociados. (Utilizando EXISTS o NOT EXISTS).
      ```sql
   SELECT nombre
   FROM departamento d
   WHERE EXISTS (
      SELECT 1
      FROM empleado e
      WHERE e.id_departamento = d.id
   );
   +------------------+
   | nombre           |
   +------------------+
   | Desarrollo       |
   | Sistemas         |
   | Recursos Humanos |
   | Contabilidad     |
   | I+D              |
   +------------------+
      ```
---
11. Devuelve los nombres de los departamentos que tienen empleados asociados. (Utilizando EXISTS o NOT EXISTS).
   ```sql
   SELECT nombre
   FROM departamento d
   WHERE NOT EXISTS (
      SELECT 1
      FROM empleado e
      WHERE e.id_departamento = d.id
   );

   +------------+
   | nombre     |
   +------------+
   | Proyectos  |
   | Publicidad |
   +------------+
   ```
---