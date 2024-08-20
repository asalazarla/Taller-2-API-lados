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
+ ________________________________________

### Punto 4.

```python
```

**Explicación:**
________________________________________

### Punto 5.

```python
```

**Explicación:**

