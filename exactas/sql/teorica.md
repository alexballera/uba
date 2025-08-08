# Teoría SQL
## 8 de Agosto

```sql
-- Creación de la tabla nombre1
CREATE TABLE nombre1(
id INT PRIMARY KEY,
nombre VARCHAR(100)
);
```

```sql
-- Inserción de datos en la tabla nombre1
INSERT INTO nombre1 VALUES
(1, "Alex"),
(2, "Jose");

```

```sql
-- Actualización de datos en la tabla nombre1
UPDATE nombre1 SET id = 5 WHERE id = 1;
```

```sql
-- Actualización de datos en la tabla nombre1
UPDATE nombre1 SET nombre = "Robert" WHERE nombre = "Alex"; 
```

```sql
-- Consulta de datos en la tabla nombre1
SELECT * FROM nombre1
```

```sql
-- Eliminación de datos en la tabla nombre1
DELETE FROM nombre1 WHERE id = 1;
```

```sql
-- Eliminación de la tabla nombre1
DROP TABLE nombre1;
```

```sql

