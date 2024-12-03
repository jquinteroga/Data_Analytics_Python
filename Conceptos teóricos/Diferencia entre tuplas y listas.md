
## Descripción
Tanto las tuplas como las listas son estructuras de datos en Python que permiten almacenar colecciones de elementos. La principal diferencia radica en su mutabilidad.

## Comparación clave

| Característica  | Tuplas                                                               | Listas                                                                 |
| --------------- | -------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| **Mutabilidad** | Inmutables (no se pueden modificar después de creadas).              | Mutables (se pueden modificar).                                        |
| **Sintaxis**    | Se definen con paréntesis `()`                                       | Se definen con corchetes `[]`                                          |
| **Rendimiento** | Más rápidas y eficientes en memoria debido a su inmutabilidad.       | Más lentas y consumen más memoria.                                     |
| **Uso típico**  | Datos que no cambian, como coordenadas o configuraciones constantes. | Datos que cambian frecuentemente, como listas de tareas o inventarios. |

## Ejemplo
```python
# Definición de una tupla
mi_tupla = (1, 2, 3)

# Definición de una lista
mi_lista = [1, 2, 3]

# Intento de modificar
# mi_tupla[0] = 10  # Error: las tuplas son inmutables
mi_lista[0] = 10  # Correcto: las listas son mutables

print(mi_tupla)  # Salida: (1, 2, 3)
print(mi_lista)  # Salida: [10, 2, 3]
```

