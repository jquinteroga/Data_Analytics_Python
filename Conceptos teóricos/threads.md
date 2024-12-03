Los **hilos** (o **threads**) son la unidad más pequeña de ejecución dentro de un proceso. Permiten dividir un programa en tareas más pequeñas que pueden ejecutarse de manera concurrente, aprovechando el paralelismo a nivel de software o hardware. Los hilos comparten los mismos recursos y memoria de su proceso padre, lo que los hace más ligeros que los procesos completos.

---

### **Características principales de los hilos:**

1. **Concurrentes:**
    
    - Los hilos pueden ejecutarse simultáneamente en sistemas con múltiples núcleos o de manera concurrente (aparente simultaneidad) en sistemas de un solo núcleo.
2. **Ligereza:**
    
    - Comparados con los procesos, los hilos tienen un costo menor en términos de memoria y tiempo de creación, ya que comparten el mismo espacio de memoria.
3. **Compartición de recursos:**
    
    - Los hilos de un mismo proceso comparten datos, variables globales, archivos abiertos, etc.
4. **Independencia relativa:**
    
    - Aunque comparten recursos, los hilos tienen su propio contador de programa, pila y registros.

---

### **¿Cómo funcionan los hilos en Python?**

En Python, los hilos se gestionan mediante la biblioteca estándar `threading`. Sin embargo, debido al _Global Interpreter Lock_ (GIL), solo un hilo puede ejecutar bytecode de Python a la vez. Esto limita el verdadero paralelismo en Python puro, pero aún es útil para tareas que no dependen del CPU, como operaciones de entrada/salida (E/S).

---

### **Ventajas de usar hilos:**

1. **Facilitan la concurrencia:**
    
    - Los hilos permiten realizar múltiples tareas a la vez, como descargar archivos mientras se procesa información.
2. **Aprovechamiento del hardware:**
    
    - En sistemas con múltiples núcleos, los hilos pueden ejecutarse simultáneamente en núcleos separados.
3. **Intercambio de datos más eficiente:**
    
    - Compartir datos entre hilos es más rápido que hacerlo entre procesos, ya que los hilos comparten el mismo espacio de memoria.

---

### **Limitaciones de los hilos:**

1. **Competencia por recursos:**
    
    - Si no se gestionan correctamente, los hilos pueden interferir entre sí, causando problemas como _race conditions_.
2. **Complejidad:**
    
    - El manejo de múltiples hilos puede ser difícil, especialmente cuando se necesita sincronización entre ellos.
3. **Global Interpreter Lock (GIL):**
    
    - En Python, el GIL impide que múltiples hilos ejecuten bytecode de Python en paralelo, lo que limita su utilidad en tareas intensivas de CPU.

---

### **Ejemplo básico con `threading`:**

```python
import threading
import time

def tarea(nombre):
    print(f"Iniciando tarea: {nombre}")
    time.sleep(2)
    print(f"Tarea completada: {nombre}")

# Crear y ejecutar hilos
hilo1 = threading.Thread(target=tarea, args=("Hilo 1",))
hilo2 = threading.Thread(target=tarea, args=("Hilo 2",))

hilo1.start()
hilo2.start()

hilo1.join()
hilo2.join()

print("Todas las tareas han terminado.")
```

#### **Salida:**

```
Iniciando tarea: Hilo 1
Iniciando tarea: Hilo 2
Tarea completada: Hilo 1
Tarea completada: Hilo 2
Todas las tareas han terminado.
```

---

### **¿Cuándo usar hilos?**

- **Operaciones de E/S concurrentes:** Descargar archivos, leer datos de una base de datos, manejar sockets.
- **Tareas que requieren poco cálculo intensivo:** Animaciones, interfaces gráficas.

Para tareas intensivas de CPU, se recomienda usar **procesos** (`multiprocessing`) en lugar de hilos para evitar el impacto del GIL en Python.

# Temas relacionados:
- [[multiprocessing]]
