# Taller-2-API-lados
____________________________________ 

## Desarrollo del Taller 2 en la asignatura de Programacion de Computadores - UNAL
Coordial saludo, nuestro grupo de Programacion se llama API-lados, a continuacion presentamos nuestro grandioso logo.

[![Whats-App-Image-2024-02-28-at-9-47-06-AM.jpg](https://i.postimg.cc/W4qjTqyc/Whats-App-Image-2024-02-28-at-9-47-06-AM.jpg)](https://postimg.cc/rdT79scf)

## Integrantes:
+ Michael Kaleth Mora Mejia (1086774311)
+ Angie Carolina Salazar Lara (1052837889)
+ Alejandro	Urrego Valencia (1000364014)
__________________________________
## Desarrollo 
### Punto 11 BONO.
A continuacion, el programa en Python que determina si una matriz cuadrada es magica. **NOTA**: *Una matriz es magica si la suma de cada una de sus filas, columnas y diagonales es la misma*.

**Enfoque**:
+ Primero, calculamos la suma de la primera fila. Esta suma servira como referencia.
+ Luego, verificamos si todas las demas filas, columnas y diagonales tienen la misma suma que la referencia.
+ Si alguna fila, columna o diagonal no coincide con la suma de referencia, la matriz no es magica.

```python
def es_matriz_magica(matriz):
    n = len(matriz)  # tamaño de la matriz (n x n)
    
    # calc la + de la primera fila como referencia
    suma_referencia = 0
    for j in range(n):
        suma_referencia += matriz[0][j]
    
    # verifica si todas las filas tienen la misma +
    for i in range(1, n):
        suma_fila = 0
        for j in range(n):
            suma_fila += matriz[i][j]
        if suma_fila != suma_referencia:
            return False
    
    # verfica si todas las columnas tienen la misma +
    for j in range(n):
        suma_columna = 0
        for i in range(n):
            suma_columna += matriz[i][j]
        if suma_columna != suma_referencia:
            return False
    
    # verifica la + de la diagonal principal
    suma_diagonal_principal = 0
    for i in range(n):
        suma_diagonal_principal += matriz[i][i]
    if suma_diagonal_principal != suma_referencia:
        return False
    
    # verfica la + de la diagonal secundaria
    suma_diagonal_secundaria = 0
    for i in range(n):
        suma_diagonal_secundaria += matriz[i][n - i - 1]
    if suma_diagonal_secundaria != suma_referencia:
        return False
    
    # SI todas las + son =, la matriz es |magica|
    return True

# ejemplo

# definimos una matriz 
matriz = [
    [2, 7, 6],
    [9, 5, 1],
    [4, 3, 8]
]

# llama a la funcion para verif si la matriz es |magica|
if es_matriz_magica(matriz):
    print("La matriz es magica.")
else:
    print("La matriz no es magica.")
```

**Explicacion:**
1. Funcion `es_matriz_magica(matriz)`:
   + Parametro: `matriz` es una lista de listas que representa la matriz cuadrada.
   + Variable `n`: Determina el tamaño de la matriz `(n x n)`.
   + Suma de referencia: Se calcula la suma de la primera fila y se usa como referencia.
    
2. Verificacion de filas:
    + Se verifica si la suma de cada fila es igual a la suma de referencia.

3. Verificacion de columnas:
    + Se verifica si la suma de cada columna es igual a la suma de referencia.

4. Verificacion de diagonales:
    + Se calcula y compara la suma de la diagonal principal (de la esquina superior izquierda a la inferior derecha).
    + Se calcula y compara la suma de la diagonal secundaria (de la esquina superior derecha a la inferior izquierda).

5. Resultado:
    + Si todas las sumas coinciden con la referencia, la funcion devuelve `True`, indicando que la matriz es `magica`.
    + De lo contrario, devuelve `False`.
   
________________________________________
### Punto 1. 
Desarrollar un programa que ingrese un numero entero n y separe todos los digitos que componen el numero. Pista: Utilice los operadores modulo (%) y division entera (//).

```python
# Prog para separar los digitos de un numero entero

numero = int(input("Ingresa un numero entero: "))

#Lista para almacenar los dig
digitos = []

# verificar si el numero es -
if numero < 0:
    numero = -numero  # Convertir a +

# usar ciclo while 
while numero > 0:
    digito = numero % 10 
    digitos.append(digito) 
    numero = numero // 10  # quitar ultimo dig del num

# invertir la lista de dig pq se agregaron al rev

digitos.reverse()
```

**Explicacion:**

El objetivo de este programa es tomar un numero entero `n` y separar todos los digitos que lo componen. Para lograrlo, el programa utiliza los operadores modulo `(%)` y division entera `(//)`. 
+ **Entrada**: Se solicita al usuario que ingrese un numero entero mediante `input()` y se convierte a entero con `int()`.

+ **Lista digitos**: Inicializamos una lista vacia para almacenar los digitos extraidos.

+ **Bucle while**: Continuamos extrayendo digitos mientras n sea mayor que cero.

    - Usamos n % 10 para obtener el ultimo digito del numero.
    - Ese digito se añade a la lista digitos.
    - Luego, eliminamos el ultimo digito del numero usando n = n // 10.
+ **Salida**: Finalmente, se imprime la lista digitos, que contiene los digitos del numero en orden inverso al que se extrajeron.

Es un enfoque simple pero efectivo.

________________________________________

### Punto 2.

```python
```

**Explicacion:**

_________________________________________
### Punto 3. 
Desarrollar un programa que permita ingresar dos numeros enteros y determinar si se tratan de numeros espejos, definiendo numeros espejos como dos numeros a y b tales que a se lee de izquierda a derecha igual que se lee b de derecha a izquierda, y viceversa.
```python
    # inicio de la variable que almacenara el numero invertido
    invertido = 0
    
    # mientras queden dig en n
    while n > 0:
        # obtenemos el ult dig de n
        ultimo_digito = n % 10
        # dezplamaos los dig ya invertidos a la izquierda (X por 10) y + el ult dig
        invertido = invertido * 10 + ultimo_digito
        # quitamos el ult dig de n
        n = n // 10
    
    # retornamos el num invertido
    return invertido

def son_espejos(a, b):
    # invertimos el num a
    a_invertido = invertir_numero(a)
    
    # comparar el num invertido de a con b
    if a_invertido == b:
        return True
    else:
        return False

numero1 = int(input("Ingresa el primer numero: "))
numero2 = int(input("Ingresa el segundo numero: "))

# verifica si son nums espejos
if son_espejos(numero1, numero2):
    print("Los numeros son espejos.")
else:
    print("Los numeros no son espejos.")
```

**Explicacion:**
Un numero espejo es un par de numeros donde uno es la version invertida del otro. Por ejemplo, 123 y 321 son numeros espejos porque si se invierte el numero 123, se obtiene 321.

Para resolver el problema:

+ **Invertir un numero**: Se puede invertir un numero al reves usando operaciones matematicas. Se obtiene el ultimo digito utilizando el modulo `(%)` y se elimina el ultimo digito utilizando la division entera `(//)`. Luego, se construye el numero invertido sumando estos digitos en orden inverso.
+ **Comparar los numeros**: Despues de invertir uno de los numeros, se compara con el otro para determinar si son espejos.
________________________________________

### Punto 4.

```python
```

**Explicacion:**
________________________________________

### Punto 5.
Para determinar el Minimo Comun Multiplo (MCM) de dos numeros enteros, podemos usar la relacion entre el MCM y el Maximo Comun Divisor (MCD) de dos numeros. Esta relacion se expresa como:

$$\\text{MCM}(a, b) = \frac{|a \times b|}{\text{MCD}(a, b)}\$$ 

Donde $$|a x b|$$ es el valor absoluto del producto de los dos numeros.

**Algoritmo de Euclides para el MCD**

El MCD se puede calcular de manera eficiente usando el Algoritmo de Euclides, que se basa en la siguiente idea: <p>MCD(<em>a</em>, <em>b</em>) = MCD(<em>b</em>, <em>a</em> % <em>b</em>)</p>


Este proceso se repite hasta que uno de los numeros sea cero, y el otro numero es el MCD.



**Enfoque Iterativo**

```python
def mcd_iterativo(a, b):
    # usamos el algoritmo de Euclides de manera iterativa
    while b != 0:
        a, b = b, a % b
    return a

def mcm(a, b):
    # se calcula el MCM usando la relacion entre MCM y MCD
    return abs(a * b) // mcd_iterativo(a, b)

# ingresa dos num enteros
numero1 = int(input("Ingresa el primer numero: "))
numero2 = int(input("Ingresa el segundo numero: "))

# calcula el MCM y lo muestra
resultado = mcm(numero1, numero2)
print(f"El minimo comun Multiplo de {numero1} y {numero2} es: {resultado}")

```
**Enfoque Recursivo**

```python
def mcd_recursivo(a, b):
    # usamos el algoritmo de Euclides de manera recursiva
    if b == 0:
        return a
    else:
        return mcd_recursivo(b, a % b)

def mcm(a, b):
    # se calcula el MCM usando la relacion entre MCM y MCD
    return abs(a * b) // mcd_recursivo(a, b)

# ingresa dos num enteros
numero1 = int(input("Ingresa el primer numero: "))
numero2 = int(input("Ingresa el segundo numero: "))

# calcula el MCM y lo muestra
resultado = mcm(numero1, numero2)
print(f"El minimo comun Multiplo de {numero1} y {numero2} es: {resultado}")
```

**Explicacion:**
1. Calculo del MCD (iterativo y recursivo):
+ *Iterativo*: Utilizamos un ciclo `while` para aplicar el Algoritmo de Euclides. Continuamos intercambiando `a` y `b` con `b` y `a % b` hasta que `b` sea 0. El valor de a en ese momento es el MCD.
+ *Recursivo*: Aplicamos el Algoritmo de Euclides recursivamente. Si `b` es 0, el MCD es a. Si no, llamamos recursivamente a la funcion con `b` y `a % b`.

2. Calculo del MCM:
+ Usamos la formula $$\\text{MCM}(a, b) = \frac{|a \times b|}{\text{MCD}(a, b)}\$$ para calcular el MCM de los dos numeros.
+ Utilizamos la funcion del MCD (ya sea la iterativa o la recursiva) para obtener el MCD y luego calcular el MCM.

3. Entrada:
+ El programa solicita que ingrese dos numeros enteros y luego calcula y muestra el MCM utilizando las funciones definidas.
________________________________________

### Punto 6.

```python
```

**Explicacion:**
________________________________________
### Punto 7.

```python
```

**Explicacion:**
________________________________________
### Punto 8.

```python
```

**Explicacion:**
________________________________________
### Punto 9.

```python
```

**Explicacion:**
________________________________________
### Punto 10.

```python
```

**Explicacion:**
________________________________________

