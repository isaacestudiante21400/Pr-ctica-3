# Práctica: Gestión Avanzada de Ramas y Resolución de Conflictos

---

## Preparación del entorno

### 1. Crear directorio y acceder
![Captura](capturas/1.base_preparacion_entorno/1.png)

### 2. Crear `index.html`
![Captura](capturas/1.base_preparacion_entorno/2.png)

### 3. Añadir y confirmar
![Captura](capturas/1.base_preparacion_entorno/3.png)

---

## Parte 1: Desarrollo en paralelo

### 1. Crear las tres ramas
![Captura](capturas/2.desarrollo_proyecto_parte1/1.png)
![Captura](capturas/2.desarrollo_proyecto_parte1/2.png)

### 2. Rama `cabecera`
![Captura](capturas/2.desarrollo_proyecto_parte1/3.png)
![Captura](capturas/2.desarrollo_proyecto_parte1/4.png)

### 3. Rama `contenido`
![Captura](capturas/2.desarrollo_proyecto_parte1/5.png)
![Captura](capturas/2.desarrollo_proyecto_parte1/6.png)

### 4. Rama `pie`
![Captura](capturas/2.desarrollo_proyecto_parte1/7.png)
![Captura](capturas/2.desarrollo_proyecto_parte1/8.png)

---

## Parte 2: Integración (fusiones sin conflicto)

### 1. Fusionar las ramas
![Captura](capturas/3.desarrollo_proyecto_parte2/1.png)

### 2. Unificar el código en `index.html`
![Captura](capturas/3.desarrollo_proyecto_parte2/2.png)

### 3. Commit de consolidación y eliminar las ramas de desarrollo
![Captura](capturas/3.desarrollo_proyecto_parte2/3.png)

---

## Parte 3: Provocar y resolver un conflicto

### 1. Crear la rama `rediseño`
![Captura](capturas/4.desarrollo_proyecto_parte3/1.png)

### 2. Modificar el `<h1>` y confirmar
![Captura](capturas/4.desarrollo_proyecto_parte3/2.png)
![Captura](capturas/4.desarrollo_proyecto_parte3/3.png)

### 3. Modificar el `<h1>` otra vez en main y confirmar
![Captura](capturas/4.desarrollo_proyecto_parte3/4.png)
![Captura](capturas/4.desarrollo_proyecto_parte3/5.png)

### 4. Fusionar (conflicto)
![Captura](capturas/4.desarrollo_proyecto_parte3/6.png)

### 5. Archivo con las marcas de conflicto
![Captura](capturas/4.desarrollo_proyecto_parte3/7.png)

### 6. Arreglar
![Captura](capturas/4.desarrollo_proyecto_parte3/8.png)

### 7. Terminar fusión
![Captura](capturas/4.desarrollo_proyecto_parte3/9.png)

---

## Parte 4: Ver historial

![Captura](capturas/4.desarrollo_proyecto_parte3/10.png)

---

## Reflexión teórica

### ¿Por qué ocurrió el conflicto en la Parte 3 y no en la Parte 2?

En la Parte 3 hubo conflicto porque main y rediseño cambiaron la misma línea de index.html, el h1, partiendo del mismo punto. Al intentar fusionarlas, Git compara las dos versiones con la original y se encuentra con dos cambios distintos en el mismo sitio. Como no sabe cuál de los dos es el bueno, no fusiona y te deja unas marcas donde hay error.
En la Parte 2 no pasa porque con cada rama se ha creado un archivo diferente (header.html, content.html y footer.html). Al no tocar ninguna las mismas líneas, los cambios no se superponen entre sí y Git los puede juntar sin errores.

### Al ejecutar `git switch main` en la Parte 3.2, ¿qué ocurrió con los archivos del directorio de trabajo?

Al hacer git switch main, Git mueve HEAD para que apunte a main y cambia los archivos de la carpeta para que coincidan con el último commit de esa rama. Por eso, el index.html vuelve a tener el h1 de antes del rediseño, el c5. Ese cambio no se pierde, sigue guardado en el commit C6 de la rama rediseño, y reaparece si vuelvo a esa rama.
