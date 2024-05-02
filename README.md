# OPERADOR MORSA
El operador morsa, también conocido como el operador de asignación de expresiones de fusión, es una característica relativamente nueva del lenguaje. Apareció por primera vez en 2019 con el lanzamiento de la versión 3.8. El operador se representa mediante dos puntos seguidos de un signo igual (:=). Su principal función es permitir la asignación de valores a variable dentro de una expresión, al mismo tiempo que se evalúa esta. Se le conoce cariñosamente como “el operador de la morsa” debido a su parecido con los ojos y colmillos de una morsa.


## Asignación de variables en condicionales
Uno de los usos más habituales del operador morsa es dentro de los condicionales. Es posible que sea necesario realizar una operación, comprobar si cumple una condición y sacar el valor por pantalla. Esto, antes de la aparición del operador morsa se debía hacer en varias líneas.
> 
**EJEMPLO**:
python
suma = a + b
if suma > 100:
    print(f'La suma es {suma}')
Una operación que se puede simplificar mucho con esta operación.

if (suma:= a + b) > 100:
    print(f'La suma es {suma}')


En este caso, gracias al uso del operador morsa, se puede asignar la suma de a mas b a la variable sumaen el propio if y usar posteriormente dentro de la función print(). Lo que hace el código mucho más compacto.

## Asignación de variables en bucles
Otro posible uso del operador aparece en los bucles, pudiendo asignar el valor en el momento que se valida. Por ejemplo, en un bucle while en el que se está procesando un archivo se puede cargar la línea de esta antes de procesarla.
> ejemplo:
python
while (linea := archivo.readline()) != "":
    procesar_linea(linea)
Sin el operador, el código necesario sería bastante más complejo.

linea = archivo.readline()
while linea != "":
    procesar_linea(linea)
    
    linea = archivo.readline()


## Asignación de variables en listas por comprensión
Gracias a las listas por comprensión de Python se puede escribir código compacto y elegante. Pero qué pasa si necesitamos filtrar en base al resultado de una función e incluir este resultado en la lista. En este caso el código tendría que ser cómo el siguiente.
> 
**ejemplo**:
python
[calcular_resultado(x) for x in lista_valores if calcular_resultado(x) > 0]
Lo que implica ejecutar hasta dos veces la función sobre todos los valores. Una opción para evitar tener que evaluar dos veces la función es aplicar la función sobre todos los valores y luego volver a iterar para filtrar.

[y for y in [calcular_resultado(x) for x in lista_valores] if y > 0]
Solución que también es complicada de leer. En este caso el uso del operador morsa de Python hace que el código sea sencillo y fácil de leer.


[res for x in lista_valores if (res := calcular_resultado(x)) > 0]