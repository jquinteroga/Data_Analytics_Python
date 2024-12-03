
# **<font color="purple">args y kwargs</font>
## *Descripción
`*args` y `**kwargs` son expresiones en Python que permiten trabajar con argumentos de longitud variable en funciones.
## Características

### args
- Representa una **tupla** de argumentos posicionales.
- Es útil cuando no se conoce de antemano cuántos argumentos posicionales se pasarán a la función.

### kwargs
- Representa un **diccionario** de argumentos con nombre (clave: valor).
- Almacena solo los argumentos ingresados con un nombre (clave).
- Los argumentos sin nombre se almacenan en `*args`.

## *Ejemplos

### Uso de *args
```python
def my_function(*args):
    print(args)

# Llamada con argumentos posicionales
my_function(1, 2, 3, 4)
# Salida: (1, 2, 3, 4)

### Uso de **kwargs
```python
def my_function(**kwargs):
    print(kwargs)

# Llamada con argumentos con nombre
my_function(a=5, b=6, c=7)
# Salida: {'a': 5, 'b': 6, 'c': 7}
```

### Combinación de args y kwargs
```python
def my_function(*args, **kwargs):
    print(f"Posicionales: {args}")
    print(f"Con nombre: {kwargs}")

# Llamada combinada
my_function(1, 2, 3, 4, a=5, b=6, c=7)
# Salida:
# Posicionales: (1, 2, 3, 4)
# Con nombre: {'a': 5, 'b': 6, 'c': 7}
```

## Casos de uso
- ***args**: Útil para funciones que procesan listas o secuencias de longitud variable.
- **kwargs**: Útil para configurar funciones con múltiples parámetros opcionales o configuraciones.


# *<font color="purple">lambda</font>

## Descripción
`lambda` es una expresión en Python que permite crear funciones anónimas, es decir, funciones sin nombre, definidas en una sola línea.

## Características
- **Simplicidad**: Se utiliza para crear funciones rápidas y de uso limitado.
- **Sintaxis compacta**: Las funciones `lambda` no requieren la palabra clave `def`.
- **Uso inmediato**: Generalmente empleadas como argumentos en funciones de orden superior como `map`, `filter` y `reduce`.

## Sintaxis
```python
lambda argumentos: expresión
```

## Ejemplo
```python
# Función lambda para sumar dos números
suma = lambda x, y: x + y

# Uso
resultado = suma(3, 5)
print(resultado)  # Salida: 8
```


# Temas relacionados

- [[itertools]] : Módulo que proporciona funciones para iterar listas.
