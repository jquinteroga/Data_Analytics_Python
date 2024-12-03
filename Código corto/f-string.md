Permiten incrustar expresiones directamente dentro de una cadena, rodeadas por llaves `{}`.

#### **Sintaxis básica:**

```python
f"texto {variable} texto"
```

- Se coloca una **`f`** (o `F`) antes de las comillas de la cadena.
- Dentro de las llaves `{}`, puedes insertar **variables, expresiones, o llamadas a funciones**.

#### **Formateo avanzado:**

#### 1. **Alinear texto**

- **Alineación a la izquierda:** `:<anchura>`
- **Alineación a la derecha:** `:>anchura`
- **Centrado:** `:^anchura`

```python
nombre = "Ana"
print(f"|{nombre:<10}|{nombre:>10}|{nombre:^10}|")
# Salida: |Ana       |       Ana|   Ana    |
```

#### 2. **Formato numérico**

- **Decimales:** `{valor:.2f}` para dos decimales.
- **Separadores de miles:** `{valor:,}`.
- **Porcentajes:** `{valor:.2%}`.

```python
pi = 3.14159265359
monto = 1234567.89

print(f"Valor de π: {pi:.2f}")      # Valor de π: 3.14
print(f"Monto: {monto:,.2f}")      # Monto: 1,234,567.89
print(f"Descuento: {0.123:.2%}")   # Descuento: 12.30%
```

#### 3. **Rellenar con caracteres**

```python
num = 42
print(f"{num:05}")  # Salida: 00042 (rellena con ceros a la izquierda)
```

---
## **Ejemplos:**

Supongamos que tenemos las variables siguientes:

```python
nombre = "Ana"
edad = 28
ciudad = "Medellín"
```



#### **Con f-strings:**

```python
print(f"Hola, mi nombre es {nombre}, tengo {edad} años y vivo en {ciudad}.")
```

**Salida:**

```
Hola, mi nombre es Ana, tengo 28 años y vivo en Medellín.
```



#### **Sin f-strings (usando `str.format`):**

```python
print("Hola, mi nombre es {}, tengo {} años y vivo en {}.".format(nombre, edad, ciudad))
```

**Salida:**

```
Hola, mi nombre es Ana, tengo 28 años y vivo en Medellín.
```



#### **Sin f-strings (usando concatenación):**

```python
print("Hola, mi nombre es " + nombre + ", tengo " + str(edad) + " años y vivo en " + ciudad + ".")
```

**Salida:**

```
Hola, mi nombre es Ana, tengo 28 años y vivo en Medellín.
```



### **Comparación de los métodos:**

|Método|Ventajas|Desventajas|
|---|---|---|
|**F-strings**|- Fácil de leer y escribir.- Permite incluir expresiones directamente.|- Requiere Python 3.6 o superior.|
|**`str.format()`**|- Compatible con versiones anteriores a Python 3.6.|- Más verboso y menos legible que las f-strings.|
|**Concatenación**|- Simple de usar en casos básicos.|- Propenso a errores.- Necesita conversión explícita de tipos.|

