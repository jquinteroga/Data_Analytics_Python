### **¿Qué hace `with`?**

El bloque **`with`** maneja automáticamente la apertura y el cierre del recurso, lo que te ayuda a evitar errores como olvidar cerrar un archivo después de usarlo.

Si ocurre un error dentro del bloque, el recurso se cierra correctamente antes de que el error sea propagado.

 La sintaxis **`with as f`** permite que el recurso se "asigne" a una variable y se use dentro de un bloque de código, asegurando que el recurso se libere correctamente al final del bloque, incluso si ocurre un error.

### **Sintaxis básica:**

```python
with <expresión> as <variable>:
    # Bloque de código donde se usa el recurso
```

- **`<expresión>`**: La expresión que proporciona el recurso (como abrir un archivo).
- **`<variable>`**: El nombre de la variable donde se almacena el recurso (por ejemplo, el archivo abierto).
- El bloque de código dentro de **`with`** puede usar la variable para interactuar con el recurso.



### **Flujo de trabajo con `with`:**

1. **Abre el recurso**: La expresión de la izquierda de `as` se evalúa, y el recurso se asigna a la variable de la derecha.
2. **Ejecuta el bloque de código**: Se ejecuta el bloque de código dentro del `with`, donde puedes usar el recurso.
3. **Cierra el recurso automáticamente**: Cuando el bloque termina, ya sea exitosamente o debido a un error, el recurso se cierra automáticamente (por ejemplo, se cierra el archivo).

---


### **Ejemplo con manejo de excepciones (con `with`):**

```python
try:
    with open('archivo.txt', 'r') as f:
        content = f.read()
        print(content)
except FileNotFoundError:
    print("El archivo no se encontró.")
```

Aquí, si el archivo no se encuentra, el **`FileNotFoundError`** se captura, pero el archivo **no necesita ser cerrado manualmente**; se cerrará automáticamente al salir del bloque `with`.

---

