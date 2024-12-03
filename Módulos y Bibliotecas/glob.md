Permite encontrar archivos y directorios usando patrones de búsqueda estilo shell (como `*.txt`).

- **Ejemplo:** Buscar todos los archivos `.txt` en un directorio:

    ```python
    import glob
    
    archivos = glob.glob("*.txt")
    print(archivos)  # ['archivo1.txt', 'archivo2.txt']
    ```



## **Funciones del módulo glob**

###  <font color="blue">1) glob.glob</font>

La función **`glob.glob()`** del módulo `glob` en Python se utiliza para buscar archivos y directorios que coincidan con un patrón específico utilizando comodines.

#### **Sintaxis básica:**

```python
import glob

glob.glob(patron, recursive=False)
```

- **`patron`**: Es el patrón que describe los archivos o directorios que deseas buscar. Puedes incluir comodines como:

- **`recursive`**: (Opcional) Si es `True`, buscará archivos en el directorio y sus subdirectorios.

**Retorno**: Una lista con las rutas de los archivos y directorios que coinciden con el patrón.


### **Patrones comunes en `glob`:**

- **`*`**: Coincide con cualquier cosa (archivos o carpetas) dentro de un directorio.
    
    ```python
    glob.glob("data/*")  # Todos los archivos y carpetas
    ```
    
- **`*.ext`**: Coincide con todos los archivos con una extensión específica.
    
    ```python
    glob.glob("data/*.txt")  # Archivos .txt
    ```
    
- **`**`**: Coincide con archivos en el directorio y en subdirectorios (necesita `recursive=True`).
    
    ```python
    glob.glob("data/**/*.txt", recursive=True)  # Archivos .txt en subdirectorios
    ```
    
- **`?`**: Coincide con un solo carácter.
    
    ```python
    glob.glob("data/archivo?.txt")  # archivo1.txt, archivo2.txt, etc.
    ```
