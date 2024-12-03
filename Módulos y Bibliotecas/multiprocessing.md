La biblioteca **`multiprocessing`** en Python permite crear y gestionar procesos en paralelo. Es útil para aprovechar múltiples núcleos de CPU y ejecutar tareas simultáneamente, mejorando el rendimiento en tareas intensivas de CPU o en operaciones que pueden dividirse en partes independientes.

---

### **Características principales de `multiprocessing`:**

1. **Soporte de múltiples procesos:** Permite ejecutar varias tareas en paralelo en procesos separados, en lugar de hilos, para evitar las limitaciones del _Global Interpreter Lock_ (GIL) en Python.
2. **Compartición de datos:** Proporciona herramientas para que los procesos puedan compartir información entre sí, como colas, tuberías y valores compartidos.
3. **Similaridad con `threading`:** La interfaz es similar a la de la biblioteca `threading`, lo que facilita su uso si estás familiarizado con hilos.

---

### **Funciones y clases principales:**

1. **`Process`:** Clase para crear y gestionar procesos.
    
    ```python
    from multiprocessing import Process
    
    def say_hello():
        print("Hola desde un proceso")
    
    if __name__ == "__main__":
        p = Process(target=say_hello)
        p.start()  # Inicia el proceso
        p.join()   # Espera a que el proceso termine
    ```
    
2. **`Pool`:** Clase para manejar un grupo de procesos y distribuir tareas.
    
    ```python
    from multiprocessing import Pool
    
    def square(x):
        return x * x
    
    if __name__ == "__main__":
        with Pool(4) as pool:  # Crea un grupo de 4 procesos
            results = pool.map(square, [1, 2, 3, 4, 5])
        print(results)  # [1, 4, 9, 16, 25]
    ```
    
3. **Colas y tuberías (`Queue` y `Pipe`):** Para comunicación entre procesos.
    
    ```python
    from multiprocessing import Queue
    
    def producer(queue):
        queue.put("Mensaje desde el productor")
    
    def consumer(queue):
        print(queue.get())  # Obtiene el mensaje
    
    if __name__ == "__main__":
        q = Queue()
        p1 = Process(target=producer, args=(q,))
        p2 = Process(target=consumer, args=(q,))
        p1.start()
        p2.start()
        p1.join()
        p2.join()
    ```
    
4. **Valores y arreglos compartidos (`Value` y `Array`):** Permiten compartir datos entre procesos.
    
    ```python
    from multiprocessing import Value
    
    def increment(shared_value):
        with shared_value.get_lock():  # Asegura acceso único
            shared_value.value += 1
    
    if __name__ == "__main__":
        counter = Value('i', 0)  # Entero inicializado en 0
        processes = [Process(target=increment, args=(counter,)) for _ in range(10)]
        for p in processes:
            p.start()
        for p in processes:
            p.join()
        print(counter.value)  # Salida: 10
    ```
    

---

### **Ventajas de `multiprocessing`:**

1. **Evita el GIL:** Cada proceso tiene su propio intérprete de Python y memoria, lo que permite usar varios núcleos de CPU.
2. **Mejora de rendimiento:** Es ideal para tareas intensivas de CPU, como cálculos matemáticos complejos.
3. **Paralelismo verdadero:** Ejecuta procesos en paralelo en lugar de pseudo-paralelismo (como con `threading`).

---

### **Limitaciones:**

1. **Sobrecarga de procesos:** Crear procesos puede ser más costoso que usar hilos, especialmente para tareas ligeras.
2. **Complejidad:** Gestionar datos compartidos y comunicación entre procesos puede complicarse.
3. **Compatibilidad:** Algunos sistemas operativos pueden tener restricciones (como en Windows, donde es necesario usar `if __name__ == "__main__":`).

---

### **Casos de uso típicos:**

1. Procesamiento de grandes conjuntos de datos en paralelo.
2. Tareas intensivas de cálculo (como simulaciones científicas).
3. Automatización y programación concurrente en aplicaciones distribuidas.

# Temas relacionados:
- [[threads]]
