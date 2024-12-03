## Descripción
En Python, `tmp` es una convención comúnmente utilizada para nombrar archivos o variables temporales. Indica que su uso es transitorio dentro del programa y que puede ser descartado o eliminado automáticamente después de un tiempo.

## Características
- **Temporalidad**: Las variables o archivos `tmp` solo son relevantes durante una parte del programa.
- **Eliminación automática**: En el caso de archivos temporales, Python proporciona módulos como `tempfile` que manejan su creación y eliminación de forma automática.

## Ejemplo de uso
```python
import tempfile

# Crear un archivo temporal
with tempfile.NamedTemporaryFile(delete=True) as tmp_file:
    print(f"Archivo temporal creado en: {tmp_file.name}")
# El archivo se elimina automáticamente al salir del bloque `with`.
```

