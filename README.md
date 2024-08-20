# Taller-2-API-lados
____________________________________ 

## Desarrollo del Taller 2 en la asignatura de Programación de Computadores - UNAL
Coordial saludo, nuestro grupo de Programacion se llama API-lados, a continuacion presentamos nuestro grandioso logo.

[![Whats-App-Image-2024-02-28-at-9-47-06-AM.jpg](https://i.postimg.cc/W4qjTqyc/Whats-App-Image-2024-02-28-at-9-47-06-AM.jpg)](https://postimg.cc/rdT79scf)

## Integrantes:
+ Michael Kaleth Mora Mejia (1086774311)
+ Angie Carolina Salazar Lara (1052837889)
+ Alejandro	Urrego Valencia (1000364014)
__________________________________
## Desarrollo 
### Punto BONO.

```python
```

**Explicación:**
________________________________________
### Punto 1. 
Desarrollar un programa que ingrese un número entero n y separe todos los digitos que componen el número. Pista: Utilice los operadores módulo (%) y división entera (//).

```python
# Prog para separar los digitos de un numero entero

numero = int(input("Ingresa un número entero: "))

#Lista para almacenar los dig
digitos = []

# verificar si el número es -
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

**Explicación:**

El objetivo de este programa es tomar un número entero `n` y separar todos los dígitos que lo componen. Para lograrlo, el programa utiliza los operadores módulo `(%)` y división entera `(//)`. 
+ **Entrada**: Se solicita al usuario que ingrese un número entero mediante `input()` y se convierte a entero con `int()`.

+ **Lista digitos**: Inicializamos una lista vacía para almacenar los dígitos extraídos.

+ **Bucle while**: Continuamos extrayendo dígitos mientras n sea mayor que cero.

    - Usamos n % 10 para obtener el último dígito del número.
    - Ese dígito se añade a la lista digitos.
    - Luego, eliminamos el último dígito del número usando n = n // 10.
+ **Salida**: Finalmente, se imprime la lista digitos, que contiene los dígitos del número en orden inverso al que se extrajeron.

Es un enfoque simple pero efectivo.

________________________________________

### Punto 2.

```python
```

**Explicación:**

_________________________________________
### Punto 3. 
Desarrollar un programa que permita ingresar dos números enteros y determinar si se tratan de números espejos, definiendo números espejos como dos números a y b tales que a se lee de izquierda a derecha igual que se lee b de derecha a izquierda, y viceversa.
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

**Explicación:**
Un numero espejo es un par de números donde uno es la versión invertida del otro. Por ejemplo, 123 y 321 son números espejos porque si se invierte el número 123, se obtiene 321.

Para resolver el problema:

+ **Invertir un número**: Se puede invertir un número al revés usando operaciones matemáticas. Se obtiene el último dígito utilizando el módulo `(%)` y se elimina el último dígito utilizando la división entera `(//)`. Luego, se construye el número invertido sumando estos dígitos en orden inverso.
+ **Comparar los números**: Después de invertir uno de los números, se compara con el otro para determinar si son espejos.
________________________________________

### Punto 4.

```python
```

**Explicación:**
________________________________________

### Punto 5.
Para determinar el Mínimo Común Múltiplo (MCM) de dos números enteros, podemos usar la relación entre el MCM y el Máximo Común Divisor (MCD) de dos números. Esta relación se expresa como:

$$\\text{MCM}(a, b) = \frac{|a \times b|}{\text{MCD}(a, b)}\$$ 

Donde $$|a x b|$$ es el valor absoluto del producto de los dos números.

**Algoritmo de Euclides para el MCD**
El MCD se puede calcular de manera eficiente usando el Algoritmo de Euclides, que se basa en la siguiente idea:

$$\\text{MCD}(a, b) = \text{MCD}(b, a \% b)\$$

Este proceso se repite hasta que uno de los números sea cero, y el otro número es el MCD.



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
numero1 = int(input("Ingresa el primer número: "))
numero2 = int(input("Ingresa el segundo número: "))

# calcula el MCM y lo muestra
resultado = mcm(numero1, numero2)
print(f"El Mínimo Común Múltiplo de {numero1} y {numero2} es: {resultado}")

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
numero1 = int(input("Ingresa el primer número: "))
numero2 = int(input("Ingresa el segundo número: "))

# calcula el MCM y lo muestra
resultado = mcm(numero1, numero2)
print(f"El Mínimo Común Múltiplo de {numero1} y {numero2} es: {resultado}")
```

**Explicación:**
1. Cálculo del MCD (iterativo y recursivo):
+ *Iterativo*: Utilizamos un ciclo `while` para aplicar el Algoritmo de Euclides. Continuamos intercambiando `a` y `b` con `b` y `a % b` hasta que `b` sea 0. El valor de a en ese momento es el MCD.
+ *Recursivo*: Aplicamos el Algoritmo de Euclides recursivamente. Si `b` es 0, el MCD es a. Si no, llamamos recursivamente a la función con `b` y `a % b`.

2. Cálculo del MCM:
+ Usamos la fórmula $$\\text{MCM}(a, b) = \frac{|a \times b|}{\text{MCD}(a, b)}\$$ para calcular el MCM de los dos números.
+ Utilizamos la función del MCD (ya sea la iterativa o la recursiva) para obtener el MCD y luego calcular el MCM.

3. Entrada:
+ El programa solicita que ingrese dos números enteros y luego calcula y muestra el MCM utilizando las funciones definidas.
________________________________________

### Punto 6.

```python
```

**Explicación:**
________________________________________
### Punto 7.

```python
```

**Explicación:**
________________________________________
### Punto 8.

```python
```

**Explicación:**
________________________________________
### Punto 9.

```python
```

**Explicación:**
________________________________________
### Punto 10.

```python
```

**Explicación:**
________________________________________

