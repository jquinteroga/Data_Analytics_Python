### **1. `filter()`**
Filtra los elementos de un iterable según una condición. Devuelve un iterador con los elementos que cumplen dicha condición.

- **Ejemplo:**
   ```python
   list_a = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
   resultado = list(filter(lambda element: element > 4, list_a))
   print(resultado)  # [5, 6, 7, 8, 9]
   ```

   **Explicación:**
   - Se pasa una función lambda `lambda element: element > 4`, que evalúa si el elemento es mayor que 4.
   - `filter` retorna solo los elementos que cumplen esta condición: `[5, 6, 7, 8, 9]`.

---

### **2. `map()`**
Aplica una función a cada elemento de un iterable y devuelve un iterador con los resultados.

- **Ejemplo:**
   ```python
   list_a = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
   resultado = list(map(lambda element: element + 10, list_a))
   print(resultado)  # [10, 11, 12, 13, 14, 15, 16, 17, 18, 19]
   ```

   **Explicación:**
   - Se pasa una función lambda `lambda element: element + 10`, que suma 10 a cada elemento de `list_a`.
   - El resultado es una nueva lista donde cada valor se ha incrementado en 10.

---

### **3. `reduce()`**
Reduce un iterable aplicando una función acumulativa a sus elementos, hasta que queda un único valor. Para usar `reduce`, es necesario importarlo desde `functools`.

- **Ejemplo:**
   ```python
   from functools import reduce

   my_list = [1, 2, 3, 4, 5, 6]
   resultado = reduce(lambda item_1, item_2: item_1 + item_2, my_list)
   print(resultado)  # 21
   ```

   **Explicación:**
   - La función lambda `lambda item_1, item_2: item_1 + item_2` toma dos elementos y los suma.
   - `reduce` aplica esta función acumulativamente:  
     ```
     ((((1 + 2) + 3) + 4) + 5) + 6 = 21
     ```

---

### **Resumen de diferencias:**
| Función   | ¿Qué hace?                                           | Devuelve       |
|-----------|------------------------------------------------------|----------------|
| `filter`  | Filtra elementos que cumplen una condición.          | Iterador       |
| `map`     | Aplica una función a cada elemento.                  | Iterador       |
| `reduce`  | Reduce los elementos a un único valor usando una función acumulativa. | Valor único |

---

### **Uso combinado:**
Estas funciones pueden combinarse para realizar operaciones más complejas.

**Ejemplo:**
Filtrar números mayores a 2, sumarles 10 y calcular el total:
```python
from functools import reduce

list_a = [0, 1, 2, 3, 4, 5]
resultado = reduce(
    lambda x, y: x + y,
    map(
        lambda x: x + 10,
        filter(lambda x: x > 2, list_a)
    )
)
print(resultado)  # 57
```

**Explicación:**
1. `filter(lambda x: x > 2, list_a)` → Filtra `[3, 4, 5]`.
2. `map(lambda x: x + 10, ...)` → Suma 10 a cada elemento → `[13, 14, 15]`.
3. `reduce(lambda x, y: x + y, ...)` → Suma los elementos → `13 + 14 + 15 = 57`.

## Temas relacionados

- [[Collections]] : Encontrarás métodos de dicha colección que se pueden usar en listas.
