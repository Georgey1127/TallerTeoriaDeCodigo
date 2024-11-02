
# Generación y Transformación de Palabras Código con Matrices Generadoras

Este proyecto de Python proporciona un conjunto de funciones para verificar si dos matrices generadoras de códigos lineales son equivalentes, utilizando operaciones como permutación de columnas y multiplicación por un escalar en un campo finito.

## Descripción General del Código

### Funciones Principales

1. **`generate_codewords(G, q)`**:
   - Genera todas las palabras código posibles de una matriz generadora `G` en un campo finito de tamaño `q`.
   - Utiliza el producto de combinaciones lineales de las filas de `G` y las almacena en un conjunto para evitar duplicados.

2. **`find_permutation(perm)`**:
   - Determina los intercambios necesarios para transformar una lista en la permutación deseada.
   - Esta función es útil para entender las posiciones específicas en las que se permutaron las columnas de `G`.

3. **`permutaciones(G1, G2, q)`**:
   - Esta es la función principal que compara dos matrices generadoras `G1` y `G2` y verifica si son equivalentes mediante permutación de columnas, multiplicación por un escalar, o una combinación de ambas operaciones.
   - Devuelve el tipo de transformación que hace equivalentes a `G1` y `G2`, si existe alguna, y muestra las palabras código generadas por ambas matrices.

### Lógica de Verificación de Equivalencia

La función `permutaciones` evalúa la equivalencia entre las matrices `G1` y `G2` en tres pasos:

1. **Verificación de Permutación**:
   - Genera todas las permutaciones posibles de las columnas de `G1`.
   - Compara cada permutación con `G2` para verificar si existe una que haga las matrices equivalentes.
   
2. **Multiplicación por Escalar**:
   - Recorre cada columna de `G1` y multiplica sus elementos por cada escalar posible en el campo finito.
   - Compara cada resultado con `G2` para verificar si existe una transformación que las haga equivalentes.

3. **Combinación de Permutación y Multiplicación por Escalar**:
   - Aplica tanto permutación de columnas como multiplicación por escalar a `G1` para cubrir todos los casos posibles de equivalencia.

### Ejemplos de Uso

El código incluye varios ejemplos para mostrar cómo se pueden transformar `G1` y `G2` mediante operaciones permitidas:

```python
print("Ejemplo1:")
G1 = [[1, 1, 0, 0], [0, 0, 1, 1]]
G2 = [[1, 0, 1, 0], [0, 1, 0, 1]]
print(permutaciones(G1, G2, 2))

# Salida Esperada:
# Permutación entre posiciones: [(2, 3)]
# C1=(0000),(0011),(1100),(1111)
# C2=(0000),(0101),(1010),(1111)
```

## Ejecución del Código

Para ejecutar este código, necesitarás Python 3.x y la librería `numpy`.

1. **Instalar `numpy`**:
   ```bash
   pip install numpy
   ```

2. **Ejecutar el Script**:
   ```bash
   python nombre_del_script.py
   ```

### Estructura de Resultados

Cada ejecución del ejemplo mostrará el tipo de transformación (si existe) y las palabras código generadas para cada matriz.

## Notas

Este código es útil en teoría de códigos lineales para analizar equivalencia de matrices generadoras en un campo finito, ayudando a entender cómo se pueden obtener las mismas palabras código bajo transformaciones específicas.
