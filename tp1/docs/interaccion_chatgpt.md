# Interacción con chatGPT

**Prompt:**
*Dado el siguiente requerimiento “formule una función en lenguaje Python para encontrar todos los números primos entre dos límites establecidos externamente y proporcionados como parámetros”, analiza el mismo y propón mejoras para eliminar eventuales ambigüedades.*

## Análisis del requerimiento

**Respuesta de chatGPT**
"El enunciado describe qué se quiere hacer, pero presenta algunas ambigüedades o aspectos no especificados:
1. Tipo de los parámetros
No se especifica si los límites deben ser enteros. Los números primos solo están definidos para enteros positivos mayores que 1.
2. Inclusión o exclusión de los límites
No se aclara si los límites del rango son inclusivos o exclusivos.
3. Orden de los parámetros
No se indica qué ocurre si el primer límite es mayor que el segundo.
4. Validación de datos
No se especifica qué hacer si:
   - los valores son negativos
   - no son enteros
   - el rango es inválido.
5. Formato del resultado
No se indica si la función debe:
   - devolver una lista
   - imprimir los números
   - devolver un generador
   - devolver también la cantidad de primos.
6. Eficiencia o restricciones
No se menciona si el algoritmo debe considerar eficiencia para rangos grandes.
7. Nombre y estructura de la función
No se define la firma de la función (nombre, tipo de retorno)."

## Propuesta de mejora del requerimiento

**Respuesta de chatGPT**
"Una versión más clara podría ser:

Requerimiento mejorado

Desarrollar una función en Python llamada primos_en_rango(limite_inferior, limite_superior) que reciba dos números enteros como parámetros y devuelva una lista con todos los números primos comprendidos entre dichos límites, incluyendo ambos extremos si corresponden.

Condiciones:
Los parámetros deben ser números enteros.
Si limite_inferior es mayor que limite_superior, la función debe intercambiar los valores o generar una excepción.
Los números primos se consideran enteros mayores que 1.
La función debe validar los parámetros y manejar entradas inválidas.
El resultado debe ser una lista de números primos ordenados de menor a mayor."

## Implementación del código en Python
**Prompt:**
*Con el resultado del requerimiento propuesto, genera código Python para implementarlo.*

**Respuesta de chatGPT**
"Perfecto. Siguiendo la versión mejorada del requerimiento, aquí tienes una implementación en Python clara, que incluye validación de parámetros y devuelve una lista de primos dentro del rango inclusivo:"

**El código resultante para la implementación en Python, se encuentra en el directorio src/ dentro del archivo primos.ipynb**

## Casos de prueba para evaluar el código
**Prompt:**
*Con el código resultante, propón casos de prueba para evaluar el código y además proporciona el código para implementar esos casos de prueba en forma automatizada.*

**Respuesta de chatGPT**
"Perfecto. Vamos a generar casos de prueba completos y luego un script automatizado en Python para validarlos."

| Caso | Limites | Resultado esperado         | Descripción                                   |
| ---- | ------- | -------------------------- | --------------------------------------------- |
| 1    | 10, 30  | `[11, 13, 17, 19, 23, 29]` | Rango normal con varios primos                |
| 2    | 2, 2    | `[2]`                      | Rango de un solo número que es primo          |
| 3    | 0, 1    | `[]`                       | Rango sin primos (menores que 2)              |
| 4    | 30, 10  | `[11, 13, 17, 19, 23, 29]` | Límites invertidos, la función debe manejarlo |
| 5    | -5, 5   | `[2, 3, 5]`                | Rango con números negativos, se ignoran       |
| 6    | 14, 16  | `[]`                       | Rango sin primos, todos compuestos            |
| 7    | 17, 17  | `[17]`                     | Rango de un solo número que es primo          |
| 8    | 'a', 10 | `TypeError`                | Tipo inválido, debe lanzar excepción          |
| 9    | 10, 3.5 | `TypeError`                | Tipo inválido, debe lanzar excepción          |

**El código resultante para los casos de prueba se encuentra en el directorio src/ dentro del archivo primos.ipynb**