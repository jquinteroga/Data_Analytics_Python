La biblioteca **`collections`** en Python es parte de la biblioteca estándar y ofrece funcionalidades adicionales en comparación con las estructuras de datos básicas como listas, tuplas y diccionarios. 

---
### **Principales contenedores en `collections`**

#### 1. **`namedtuple`**
   - Un subtipo de tupla que permite acceder a los elementos por nombre en lugar de por índice.
   - Ideal para crear objetos ligeros e inmutables con nombres de campo.

   **Ejemplo:**
   ```python
   from collections import namedtuple

   Persona = namedtuple('Persona', ['nombre', 'edad'])
   p = Persona(nombre='Ana', edad=25)
   print(p.nombre)  # Ana
   print(p[1])      # 25
   ```

---

#### 2. **`deque`** (double-ended queue)
   - Una cola que permite agregar o eliminar elementos desde ambos extremos con eficiencia.
   - Útil para implementar colas o pilas de manera rápida.

   **Ejemplo:**
   ```python
   from collections import deque

   d = deque([1, 2, 3])
   d.append(4)       # Agrega al final
   d.appendleft(0)   # Agrega al inicio
   print(d)          # deque([0, 1, 2, 3, 4])
   d.pop()           # Elimina del final
   d.popleft()       # Elimina del inicio
   print(d)          # deque([1, 2, 3])
   ```


#### 3. **`Counter`**
   - Una subclase de diccionario diseñada para contar objetos.
   - Ideal para obtener frecuencias de elementos en una lista u otros iterables.

   **Ejemplo:**
   ```python
   from collections import Counter

   colores = ['rojo', 'azul', 'rojo', 'verde', 'azul', 'rojo']
   contador = Counter(colores)
   print(contador)  # Counter({'rojo': 3, 'azul': 2, 'verde': 1})
   print(contador['rojo'])  # 3
   print(contador.most_common(1))  # [('rojo', 3)]
   ```


#### 4. **`ChainMap`**
   - Combina varios diccionarios en una sola vista unificada.
   - Ideal para trabajar con múltiples contextos de variables.

   **Ejemplo:**
   ```python
   from collections import ChainMap

   dic1 = {'a': 1, 'b': 2}
   dic2 = {'b': 3, 'c': 4}
   cm = ChainMap(dic1, dic2)
   print(cm['b'])  # 2 (toma el valor del primer diccionario)
   print(cm['c'])  # 4
   ```

---

### **Ejemplo práctico:**
Crear un contador de palabras en un texto:
```python
from collections import Counter

texto = "hola mundo hola python python hola"
palabras = texto.split()
contador = Counter(palabras)
print(contador)  # Counter({'hola': 3, 'python': 2, 'mundo': 1})
```


# Temas relacionados
- [[Diferencia entre tuplas y listas]]
- [[defaultdict]]
