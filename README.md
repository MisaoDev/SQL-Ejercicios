# SQL-Ejercicios
Ejercicios básicos de SQL para usar con la base de datos de ejemplo [Sakila](https://dev.mysql.com/doc/sakila/en/). Las respuestas de ejemplo son para MySQL pero en gran parte son compatibles con SQL Server u otros motores.

La mayoría de los ejercicios fueron sacados de internet, traducidos o modificados. Alguno que otro es original.

## Aclaraciones
* En estos ejercicios la tabla **film** será referenciada como _**película**_, mientras que **inventory** será _**película física**_ o _**película inventariada**_.

## Queries de lectura
#### 1. Cantidad de actores por cada película
<details>
<summary>Solución</summary><p>

```sql
SELECT 
  f.film_id           AS 'ID',
  f.title             AS 'Título',
  COUNT(fa.film_id)   AS "Actores"
FROM film AS f
LEFT JOIN film_actor  AS fa ON fa.film_id = f.film_id
GROUP BY `ID`
ORDER BY `Actores` DESC;
```
</p></details>

#### 1. Muestra el nombre y apellido de todos los actores.
<details>
<summary>Solución</summary><p>

```sql
SELECT
  first_name  AS "Nombre",
  last_name   AS "Apellido"
FROM actor;
```
</p></details>

#### 2. Muestra el nombre y apellido de cada actor en una sola columna, en mayúscula. Nombra la columna "Nombre del actor".
<details>
<summary>Solución</summary><p>

```sql
SELECT
  UCASE(CONCAT_WS(" ", first_name, last_name)) AS "Nombre del actor"
FROM actor;
```

También sirve **UPPER** en lugar de **UCASE**:
```sql
SELECT
  UPPER(CONCAT_WS(" ", first_name, last_name)) AS "Nombre del actor"
FROM actor;
```
**Tip**: La función *CONCAT_WS* concatena los datos que recibe y los separa usando el primer parámetro como separador.
</p></details>

#### 3. Muestra el ID, nombre y apellido de un actor, de quien solo tienes el nombre "Joe".
<details>
<summary>Solución</summary><p>

```sql
SELECT
  actor_id    AS "ID",
  first_name  AS "Nombre",
  last_name   AS "Apellido"
FROM actor
WHERE first_name = "Joe";
```
</p></details>

#### 4. Encuentra los actores cuyo apellido contenga "GEN".
<details>
<summary>Solución</summary><p>

```sql
SELECT
  first_name  AS "Nombre",
  last_name   AS "Apellido"
FROM actor
WHERE last_name LIKE "%GEN%";
```
</p></details>

#### 5. Encuentra los actores cuyo apellido contenga "LI". Ordena las filas por apellido y nombre (en ese orden).
<details>
<summary>Solución</summary><p>

```sql
SELECT
  first_name  AS "Nombre",
  last_name   AS "Apellido"
FROM actor
WHERE last_name LIKE "%LI%"
ORDER BY last_name, first_name;
```
</p></details>

#### 6. Usando la función IN, muestra el nombre y apellido de todos los clientes llamados "Terry", "Jessie" o "Alice".
<details>
<summary>Solución</summary><p>

```sql
SELECT
  first_name  AS "Nombre",
  last_name   AS "Apellido"
FROM customer
WHERE first_name IN ("Terry", "Jessie", "Alice");
```
</p></details>

#### 7. Muestra el apellido de cada actor y la cantidad de actores que tienen ese apellido.
<details>
<summary>Solución</summary><p>

```sql
SELECT
  last_name   AS "Apellido",
  COUNT(*)    AS "Cantidad de actores"
FROM actor
GROUP BY last_name;
```
</p></details>

#### 8. Muestra el apellido y la cantidad de actores que tienen ese apellido, pero solo los apellidos compartidos por dos o más actores.
<details>
<summary>Solución</summary><p>

```sql
SELECT
  last_name   AS "Apellido",
  COUNT(*)    AS "Cantidad de actores"
FROM actor
GROUP BY last_name
HAVING `Cantidad de actores` >= 2;
```
</p></details>

#### 9. Usando _joins_, muestra el nombre, apellido y dirección de cada miembro del _staff_.
<details>
<summary>Solución</summary><p>

```sql
SELECT
  s.first_name                              AS "Nombre",
  s.last_name                               AS "Apellido",
  COALESCE(a.address, "No tiene dirección") AS "Dirección"
FROM staff AS s
JOIN address AS a ON a.address_id = s.address_id;
```
**Tip**: Cuando desplegamos datos de un campo *nullable* (que puede contener *NULL*), es conveniente usar **COALESCE** para mostrar un texto por defecto si no se encuentra un dato.
</p></details>

#### 10. placeholder
<details>
<summary>Solución</summary><p>

```sql
placeholder
```
</p></details>

#### 11. placeholder
<details>
<summary>Solución</summary><p>

```sql
placeholder
```
</p></details>

#### 12. placeholder
<details>
<summary>Solución</summary><p>

```sql
placeholder
```
</p></details>

#### 13. placeholder
<details>
<summary>Solución</summary><p>

```sql
placeholder
```
</p></details>

#### 14. placeholder
<details>
<summary>Solución</summary><p>

```sql
placeholder
```
</p></details>

#### 15. placeholder
<details>
<summary>Solución</summary><p>

```sql
placeholder
```
</p></details>

#### 16. placeholder
<details>
<summary>Solución</summary><p>

```sql
placeholder
```
</p></details>

#### 17. placeholder
<details>
<summary>Solución</summary><p>

```sql
placeholder
```
</p></details>

#### 18. placeholder
<details>
<summary>Solución</summary><p>

```sql
placeholder
```
</p></details>

#### 19. placeholder
<details>
<summary>Solución</summary><p>

```sql
placeholder
```
</p></details>

#### 20. placeholder
<details>
<summary>Solución</summary><p>

```sql
placeholder
```
</p></details>

#### 21. placeholder
<details>
<summary>Solución</summary><p>

```sql
placeholder
```
</p></details>

#### 22. placeholder
<details>
<summary>Solución</summary><p>

```sql
placeholder
```
</p></details>

#### 2. placeholder
<details>
<summary>Solución</summary><p>

```sql
placeholder
```
</p></details>

