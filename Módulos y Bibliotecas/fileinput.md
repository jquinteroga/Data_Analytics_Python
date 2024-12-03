
Leer múltiples archivos como un flujo de entrada continuo.
Proporciona funciones para iterar a través de líneas de uno o más archivos o desde la entrada estándar (como si fuera un único archivo).

**Documentación:** https://docs.python.org/es/3/library/fileinput.html

**NOTA:** Los archivos son leídos línea por línea de manera secuencial, no en paralelo.
### **Resumen de funciones**

| Función                       | Descripción                                       | Ejemplo                          |
| ----------------------------- | ------------------------------------------------- | -------------------------------- |
| **`fileinput.input()`**       | Itera sobre líneas de uno o más archivos.         | `fileinput.input(['file1.txt'])` |
| **`fileinput.filename()`**    | Devuelve el nombre del archivo actual.            | `fileinput.filename()`           |
| **`fileinput.filelineno()`**  | Retorna el número de línea en el archivo actual.  | `fileinput.filelineno()`         |
| **`fileinput.lineno()`**      | Retorna el número total de líneas procesadas.     | `fileinput.lineno()`             |
| **`fileinput.isfirstline()`** | Indica si es la primera línea del archivo actual. | `fileinput.isfirstline()`        |
| **`fileinput.close()`**       | Cierra el objeto de entrada.                      | `fileinput.close()`              |
| **`inplace=True`**            | Permite modificar archivos en su lugar.           | `fileinput.input(inplace=True)`  |

### **Funciones más usadas 

#### 1. **`fileinput.input()`**

Abre uno o más archivos para iterarlos línea por línea. Si no se pasa un archivo, lee de la entrada estándar (STDIN) [[Entrada estándar (STDIN)]].

**Sintaxis:**

```python
fileinput.input(files=None, inplace=False, backup='', mode='r', openhook=None)
```

- **`files`**: Lista de archivos a procesar (puede ser un solo archivo o varios). Si es `None`, lee de `sys.stdin`.
- **`inplace`**: Si es `True`, permite modificar los archivos en su lugar (ver ejemplo más abajo).
- **`backup`**: Especifica la extensión para crear copias de respaldo si `inplace=True`.
- **`mode`**: Modo en el que se abren los archivos (por defecto, `'r'` para leer).
- **`openhook`**: Función opcional para modificar cómo se abren los archivos.

**Ejemplo:**

```python
import fileinput

for line in fileinput.input(files=['file1.txt', 'file2.txt']):
    print(line.strip())  # Procesa línea por línea
```

---

#### 2. **`fileinput.filename()`**

Devuelve el nombre del archivo actualmente procesado.

**Ejemplo:**

```python
import fileinput

for line in fileinput.input(['file1.txt', 'file2.txt']):
    print(f"Archivo: {fileinput.filename()}, Línea: {line.strip()}")
```

---

#### 3. **`fileinput.filelineno()`**

Retorna el número de la línea actual en el archivo que se está procesando.

**Ejemplo:**

```python
import fileinput

for line in fileinput.input(['file1.txt']):
    print(f"Línea {fileinput.filelineno()}: {line.strip()}")
```

---

#### 4. **`fileinput.lineno()`**

Devuelve el número total de líneas procesadas en todos los archivos combinados.

**Ejemplo:**

```python
import fileinput

for line in fileinput.input(['file1.txt', 'file2.txt']):
    print(f"Línea global {fileinput.lineno()}: {line.strip()}")
```

---

#### 5. **`fileinput.isfirstline()`**

Devuelve `True` si la línea que se está procesando es la primera del archivo actual.

**Ejemplo:**

```python
import fileinput

for line in fileinput.input(['file1.txt', 'file2.txt']):
    if fileinput.isfirstline():
        print(f"Primera línea del archivo {fileinput.filename()}: {line.strip()}")
```

---

#### 6. **`fileinput.close()`**

Cierra el objeto de entrada. Generalmente no es necesario usarlo explícitamente si se usa con un `with`.

**Ejemplo:**

```python
import fileinput

f = fileinput.input(['file1.txt'])
for line in f:
    print(line.strip())
f.close()  # Cierra manualmente
```

---

#### 7. **Modificación en su lugar (`inplace=True`)**

Permite modificar los archivos mientras los procesas, escribiendo las líneas modificadas directamente en el archivo.

**Ejemplo:**

```python
import fileinput

for line in fileinput.input(files=['file1.txt'], inplace=True, backup='.bak'):
    print(line.replace('viejo', 'nuevo'), end='')  # Reemplaza 'viejo' por 'nuevo'
```

- **`backup='.bak'`**: Crea una copia de respaldo con la extensión `.bak`.

---


