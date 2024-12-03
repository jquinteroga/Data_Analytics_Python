Las funciones `display()` y `print()` en Python tienen usos diferentes, aunque ambas permiten mostrar información. A continuación, se presentan sus diferencias principales:

---

### 1. **`print()`**
Es una función estándar en Python para imprimir texto o datos en la consola.

- **Salida**: Representación en texto plano.
- **Uso principal**: Mostrar resultados o mensajes al usuario.
- **Formato de salida**: Convierte los objetos en cadenas (utilizando su método `str()`).
- **Limitaciones**: No está diseñada para formatos complejos o representaciones ricas.

**Ejemplo:**
```python
print("Hola, mundo!")  # Muestra: Hola, mundo!
print([1, 2, 3])       # Muestra: [1, 2, 3]
```

---

### 2. **`display()`**
Es una función proporcionada por **IPython** (usada en entornos como Jupyter Notebook) y no está incluida en la biblioteca estándar de Python. Sirve para mostrar representaciones más detalladas y ricas de objetos.

- **Salida**: Representaciones mejoradas y visualmente enriquecidas.
- **Uso principal**: Mostrar objetos en su forma más completa (como tablas, gráficos o estructuras de datos).
- **Formato de salida**: Utiliza el método `__repr__()` del objeto, a menudo en combinación con herramientas como HTML.
- **Ventajas**: Ideal para entornos interactivos donde se requiere una salida mejorada.

**Ejemplo:**
```python
from IPython.display import display

data = {"nombre": "Ana", "edad": 25}
display(data)  # Muestra una representación mejorada (en Jupyter Notebook, aparece como una tabla)
```

---

### Diferencias clave

| **Aspecto**           | **`print()`**                | **`display()`**                             |
| --------------------- | ---------------------------- | ------------------------------------------- |
| **Disponibilidad**    | Incluida en Python estándar. | Requiere `IPython` o entornos como Jupyter. |
| **Formato de salida** | Texto simple (con `str()`).  | Representación rica (con `__repr__()`).     |
| **Uso típico**        | Consola o scripts estándar.  | Entornos interactivos (Jupyter).            |
| **Soporte visual**    | Limitado a texto plano.      | Mejor para tablas, gráficos o HTML.         |

---

### ¿Cuándo usar cada una?
- Usa **`print()`** para desarrollos generales o scripts donde solo necesites mostrar texto o valores simples.
- Usa **`display()`** en **Jupyter Notebook** o entornos interactivos cuando trabajes con estructuras complejas (como pandas DataFrames, gráficos, etc.) y desees una visualización más profesional.