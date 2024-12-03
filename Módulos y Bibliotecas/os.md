El módulo **`os`** en Python es como un puente entre tu programa y el sistema operativo. Te ayuda a manejar archivos, carpetas, rutas, y también a obtener información del sistema, todo desde tu código.
### **Principales funcionalidades del módulo `os`**

1. **Trabajar con rutas y archivos (`os.path`):**
	Contiene funciones útiles para manipular rutas de archivos y directorios, como verificar si un archivo existe o unir partes de rutas.


    ```python
    import os
    
    # Verificar si un archivo o directorio existe
    print(os.path.exists("mi_archivo.txt"))  # True o False
    
    # Obtener el nombre de archivo de una ruta
    print(os.path.basename("/ruta/a/archivo.txt"))  # archivo.txt
    
    # Obtener el directorio de una ruta
    print(os.path.dirname("/ruta/a/archivo.txt"))  # /ruta/a
    
    # Unir partes de una ruta
    print(os.path.join("carpeta", "subcarpeta", "archivo.txt"))
    # Salida: carpeta/subcarpeta/archivo.txt
    ```

2. **Crear, eliminar y renombrar directorios o archivos:**

    ```python
    # Crear un directorio
    os.mkdir("mi_carpeta")
    
    # Crear un directorio y sus subdirectorios
    os.makedirs("carpeta/subcarpeta")
    
    # Renombrar un archivo o directorio
    os.rename("archivo_viejo.txt", "archivo_nuevo.txt")
    
    # Eliminar un archivo
    os.remove("archivo_nuevo.txt")
    
    # Eliminar un directorio vacío
    os.rmdir("mi_carpeta")
    ```

3. **Listar archivos en un directorio:**

    ```python
    archivos = os.listdir(".")  # Lista el contenido del directorio actual
    print(archivos)
    ```

4. **Obtener información del sistema:**
    
    ```python
    # Nombre del sistema operativo
    print(os.name)  # 'posix' (Linux/Mac) o 'nt' (Windows)
    
    # Información sobre el usuario actual
    print(os.getlogin())  # Nombre del usuario
    
    # Identificador del proceso actual
    print(os.getpid())
    ```

5. **Trabajar con variables de entorno:**
    
    ```python
    # Obtener el valor de una variable de entorno
    print(os.getenv("HOME"))  # En Linux/Mac, devuelve el directorio del usuario
    
    # Establecer una variable de entorno
    os.environ["MI_VARIABLE"] = "valor"
    
    # Verificar todas las variables de entorno
    print(os.environ)
    ```

6. **Cambiar el directorio de trabajo:**
    
    ```python
    # Mostrar el directorio actual
    print(os.getcwd())
    
    # Cambiar a otro directorio
    os.chdir("nueva_carpeta")
    print(os.getcwd())  # Ahora muestra el nuevo directorio
    ```

7. **Ejecutar comandos del sistema:**
    
    ```python
    # Ejecutar un comando de sistema (por ejemplo, listar archivos)
    os.system("ls")  # En Linux/Mac
    os.system("dir")  # En Windows
    ```
