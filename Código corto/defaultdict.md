El **`defaultdict`** es una clase en el módulo `collections` de Python. Es una subclase de los diccionarios estándar que permite definir un **valor predeterminado** para claves inexistentes, evitando errores al acceder a claves no definidas.

**Tema relacionado: [[Collections]]

### **¿Qué hace especial a `defaultdict`?**

En un diccionario estándar, intentar acceder a una clave inexistente lanza un `KeyError`. Con `defaultdict`, puedes especificar un valor predeterminado (mediante una función llamada `default_factory`) que será asignado automáticamente a cualquier clave que no exista.

---

### **Sintaxis:**

```python
from collections import defaultdict

defaultdict(default_factory)
```

- **`default_factory`:** Es una función que retorna el valor predeterminado para claves inexistentes. Puede ser un tipo de datos como `int`, `list`, `set`, `dict` o una función definida por el usuario.

---

### **Ejemplo básico:**

```python
from collections import defaultdict

# Crear un defaultdict con valor predeterminado como lista vacía
dd = defaultdict(list)

# Acceso a una clave inexistente la crea con el valor predeterminado
dd['a'].append(1)
dd['b'].append(2)
dd['a'].append(3)

print(dd)
# Salida: defaultdict(<class 'list'>, {'a': [1, 3], 'b': [2]})
```

---

### **Comparación con un diccionario estándar:**

#### **Diccionario estándar:**

```python
dic = {}
dic['a'].append(1)  # Error: KeyError
```

#### **Con `defaultdict`:**

```python
dd = defaultdict(list)
dd['a'].append(1)  # Funciona: crea la clave 'a' con una lista vacía
```

---

### **Ventajas de `defaultdict`:**

1. **Evita comprobaciones manuales:**
    
    ```python
    # Diccionario estándar
    dic = {}
    if 'a' not in dic:
        dic['a'] = []
    dic['a'].append(1)
    
    # Con defaultdict
    dd = defaultdict(list)
    dd['a'].append(1)
    ```
    
2. **Personalización del valor predeterminado:**
    
    ```python
    dd = defaultdict(lambda: "valor predeterminado")
    print(dd['clave_inexistente'])  # Salida: valor predeterminado
    ```
    
3. **Más limpio y eficiente para tareas como conteo o agrupamiento.**
    

---

### **Casos de uso comunes:**

#### **1. Contar elementos (como `Counter`):**

```python
from collections import defaultdict

texto = "hola mundo hola python"
contador = defaultdict(int)

for palabra in texto.split():
    contador[palabra] += 1

print(contador)
# Salida: defaultdict(<class 'int'>, {'hola': 2, 'mundo': 1, 'python': 1})
```

---

#### **2. Agrupar datos:**

```python
from collections import defaultdict

datos = [('fruta', 'manzana'), ('fruta', 'naranja'), ('verdura', 'zanahoria')]

agrupados = defaultdict(list)
for categoria, item in datos:
    agrupados[categoria].append(item)

print(agrupados)
# Salida: defaultdict(<class 'list'>, {'fruta': ['manzana', 'naranja'], 'verdura': ['zanahoria']})
```

---

#### **3. Inicializar estructuras complejas:**

```python
from collections import defaultdict

dd = defaultdict(dict)
dd['usuario1']['nombre'] = "Juan"
dd['usuario1']['edad'] = 30

print(dd)
# Salida: defaultdict(<class 'dict'>, {'usuario1': {'nombre': 'Juan', 'edad': 30}})
```

---

### **Limitaciones de `defaultdict`:**

1. **Creación no intencionada de claves:** Acceder a una clave inexistente la crea automáticamente con el valor predeterminado, lo que puede ser problemático si no se controla:
    
    ```python
    dd = defaultdict(int)
    print(dd['clave_inexistente'])  # Salida: 0 (y crea la clave en el diccionario)
    ```
    
2. **No es directamente serializable con `json`:** Debe ser convertido a un diccionario estándar (`dict(dd)`) antes de ser usado con JSON.
    

---

Si tienes más dudas sobre cómo utilizar `defaultdict`, ¡puedes preguntarme! 😊