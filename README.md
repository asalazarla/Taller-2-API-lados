# Taller-1-API-lados
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
### 1. Desarrollar un programa que ingrese un número entero n y separe todos los digitos que componen el número. Pista: Utilice los operadores módulo (%) y división entera (//).

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
