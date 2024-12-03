Ofrece constantes y funciones predefinidas para trabajar con cadenas, como alfabetos predefinidos, funciones de formato o plantillas.

- **Ejemplo:**

    ```python
    import string
    
    print(string.ascii_letters)  # 'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ'
    print(string.digits)         # '0123456789'
    print(string.punctuation)    # '!"#$%&\'()*+,-./:;<=>?@[\\]^_`{|}~'
    ```



### 1. **`string.whitespace`**

- **Descripción**: Devuelve una cadena con los caracteres de espacio en blanco (espacio, tabulador, salto de línea, etc.).

    ```python
    import string
    print(string.whitespace)  # " \t\n\r\x0b\x0c"
    ```

### 2. **`string.maketrans(x, y)`**

- **Descripción**: Devuelve una tabla de traducción que puede usarse con el método `translate()`. Permite mapear caracteres de una cadena a caracteres de otra.
- **Sintaxis**:

    ```python
    import string
    string.maketrans(x, y)
    ```

- **Parámetros**:
    - **`x`**: Cadena de caracteres a reemplazar.
    - **`y`**: Cadena de caracteres que reemplazarán los caracteres de `x`.
- **Ejemplo**:

    ```python
    import string
    trans = string.maketrans("abc", "123")
    print("abcdef".translate(trans))  # "123def"
    ```

    - Otra forma:

        ```python
        str.maketrans(from, to, delete)
        ```
        
        - **`from`**: Los caracteres a ser reemplazados.
        - **`to`**: Los caracteres con los que se reemplazarán los caracteres de **`from`**.
        - **`delete`**: Los caracteres que deben ser eliminados de la cadena.


### 3. **`string.capwords(s, sep=None)`**

- **Descripción**: Divide la cadena **`s`** en palabras y convierte la primera letra de cada palabra a mayúscula y el resto a minúscula.
- **Sintaxis**:
    
    ```python
    import string
    string.capwords(s, sep=None)
    ```
    
- **Parámetros**:
    - **`s`**: La cadena a procesar.
    - **`sep`**: El delimitador de las palabras. Si no se pasa, se usa el espacio como delimitador.
- **Ejemplo**:
    
    ```python
    import string
    print(string.capwords("hello world"))  # "Hello World"
    print(string.capwords("hello world", sep=" "))  # "Hello World"
    ```

