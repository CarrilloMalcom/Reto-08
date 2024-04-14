# Reto-08

### Soy Malcom Yamil Carrillo Quintero y pertenezco al grupo de "Fenomenoides", adelante se muestra nuestro logo
<details><summary>Preparense para ver el grandioso logo: </summary><p>
<div align='center'>
<figure> <img src="https://i.postimg.cc/NFbwf57S/logo-def.png" alt="Defensa Civil" width="400" height="auto"/></br>
<figcaption><b> "somos programadores, no diseñadores" </b></figcaption></figure>
</div>
</p></details><br>

## 1. Imprimir un listado con los números del 1 al 100 cada uno con su respectivo cuadrado.

``` python
if __name__=="__main__":
    for i in range(1,101): # ciclo desde 1 hasta 100
        print (f"El cuadrado de {i} es {i**2}") # imprimir "EL cuadrado de i es i^2"
```

## 2. Imprimir un listado con los números impares desde 1 hasta 999 y seguidamente otro listado con los números pares desde 2 hasta 1000.

``` python
impar:bool=True #inicializar variable impar como verdadera
if __name__=="__main__":
    for i in range(1,1001,2): # ciclo para desde 1 hasta 1000 con paso 2
        print(i) # imprimir i
    for i in range(2,1001,2): #ciclo para desde 2 hasta 1000 con paso 2
        print(i) #imprimir i
```

## 3. Imprimir los números pares en forma descendente hasta 2 que son menores o iguales a un número natural n ≥ 2 dado

``` python
if __name__=="__main__":
    n=int(input("Ingrese un numero: ")) # n es igual a la entrada de teclado
    print(f"Los números pares menores a {n} son: ") # imprimir "los numeros menores a n son:"
    if n%2!=0: # si el residuo de n/2 NO es 0
        n-=1 # n es n-1
    for i in range (n, 1, -2): #ciclo para desde n hasta 2 con paso -2
        print(i) # imprimir i
```

## 4. Imprimir los números de 1 hasta un número natural n dado, cada uno con su respectivo factorial

``` python
if __name__=="__main__":
    n=int(input("Ingrese un número: ")) # n es igual a la entrada de teclado
    f=1 # f se inicializa como 1
    for i in range(1, n+1): # ciclo para desde 1 hasta n
        for j in range(i,1,-1): #ciclo para desde i hasta 1 con paso -1
            f *= j #f es igual a f*j
        print(f"El factorial de {i} es {f}") # imprimir "El factorial de i es f"
        f=1  # f se actualiza como 1
```

## 5. Calcular el valor de 2 elevado a la potencia n usando ciclos for

``` python
if __name__=="__main__":
    n=int(input("Ingrese el exponente para elevar a 2: ")) # n es igual a la entrada de teclado
    p=1 # p se inicializa como 1
    for i in range(1,n+1): # ciclo para desde 1 hasta n
        p*=2 # p es igual p*2
    print(f"2 elevado a la {n} es igual a {p}") # imprimir "2 elevado a la n es igual a p"
```

## 6. Leer un número natural n, leer otro dato de tipo real x y calcular x^n usando ciclos for. Disclaimer: Trate de no utilizar el operador de potencia (**).

``` python
if __name__=="__main__":
    n=int(input("Ingrese un numero para el exponente: ")) # n es igual a la entrada de teclado
    x=float(input("Ingrese el número base")) #x es igual a un numero real la entrada de teclado
    p=1 # p se inicializa como 1
    for i in range(1,n+1): # ciclo para desde 1 hasta n
        p *= x # p es igual a p*x
    print(f"El valor de {x}^{n} es igual a {p}") # imprimir "El valor de x^n es igual a p"
```

##7. Diseñe un programa que muestre las tablas de multiplicar del 1 al 9.

``` python
if __name__=="__main__":
    for i in range(1,10): # ciclo para desde 1 hasta 9
        print(f"La tabla del {i}: ") # imprimir "La tabla del i:"
        for j in range(1,11): # ciclo para desde 1 hasta 10
            print(f"{i} x {j} = {i*j}") #imprimir "ixj= i*j"
```

## 8. Diseñar una función que permita calcular una aproximación de la función exponencial alrededor de 0 para cualquier valor x (real), utilizando los primeros n términos de la serie de Maclaurin. Nota: use math para traer la función exponencial y mostrar la diferencia entre el valor real y la aproximación.
``` math
e^x \approx exp(x,n) \approx \sum_{i=0}^{n}\frac{x^i}{i!}
```
``` python
from math import exp # del paquete math se importa la función exp
x=float(input("Ingrese un número real: ")) #x es igual a un numero real de la entrada de teclado
expreal=exp(x) # se inicializa expreal como el exponencial de x
suma:float=0 # suma es igual a 0
for i in range (200): # ciclo para hasta 200
    fact = 1 # fact es igual a 1
    for j in range (1, i+1,1): #ciclo para desde 1 hasta i con paso 1
        fact *= j # fact es igual a fact*j
    nuevoTermino=x**i/fact #nuevoTermino es igual a x^2/fact
    suma += nuevoTermino #suma es igual a suma + nuevoTermino
    err: float= abs(expreal-suma)/expreal*100 #err es igual al valor absoluto de expreal- suma dividido el expreal*100
    if err<=0.1: # si err es menor o igual a 0.1
        break # romper el ciclo
print(f"El exponencial real es {expreal}") # imprimir "el exponencial real es expreal"
print(f"El dado por la secuencia Maclaurin es {suma}") # imprimir "El dado por la secuencia Maclaurin es suma"
print(f"Se necesitaron {i} iteraciones para el margen de error menor a 0.1%: {err} %") # imprimir "Se necesitaron i iteraciones para el margen de error menor a 0.1%: err%"
```

## 9. Diseñar una función que permita calcular una aproximación de la función seno alrededor de 0 para cualquier valor x (real), utilizando los primeros n términos de la serie de Maclaurin. Nota: use math para traer la función seno y mostrar la diferencia entre el valor real y la aproximación.
``` math
sin(x) \approx sin(x,n) \approx \sum_{i=0}^{n} (-1)^i \frac{x^{2i+1}}{(2i+1)!}
```

``` python
from math import sin # importar la función sin del paquete math
x=int(input("Ingrese un número: ")) # x es igual al entero proveniente de la entrada de teclado
suma:float=0 # suma se inicializa como 0
sinreal=sin(x) # se inicializa sinreal como el seno de x
flag:bool=True # flag se inicializa como verdadero
i=0 # i se inicializa como 0
fact=1
def factorial (f:float): # función factorial
    for i in range(f-1, 1, -1): #ciclo para desde f-1 hasta 1 en paso -1
        f*= i # f es igual a f*i
    return f # la función retorna f
def error(suma: float): # función error
    global porcentaje # convierte la variable porcentaje creada en la función en una variable global
    err: float = abs(sinreal - suma) # err es igual al valor absoluto de sinreal menos suma
    if abs(sinreal) > 1: # si el valor absoluto de sinreal es mayor a 1
        err /= abs(sinreal) # err es igual a err dividido el valor absoluto de sinreal
    else: # sino
        err *= 100 # err es igual a err*100
    porcentaje=err #porcentaje se crea con el mismo valor de err
    if err <= 0.1: # si err menor o igual a 0.1
        return True # la función retorna verdadero
    else: # sino
        return False # la función retorna falso
if __name__=="__main__":
    while flag: # mientras flag sea verdadero
        f:int=(2*i)+1 # f es igual al entero de 2*i+1
        fact= factorial(f) #fact es igual a lo que retorne la función factorial con el argumento f
        a=(-1)**i # a es igual a (-1)^i
        b=x**f # b es igual a x^f
        nuevoTermino=a * (b / fact) #nuevoTermino es igual a (a * (b/fact))
        suma += nuevoTermino # suma es igual a suma + nuevoTermino
        i += 1 # i es igual a i+1
        if error(suma): #si la función error con el argumento suma retorna verdadero
            flag=False # flag se actualiza como falso
print(f"El valor del seno real es {sinreal}") #imprime "El valor del seno real es sinreal"
print(f"El valor gracias a la secuencia de Maclaurin es {suma}") # imprime "El valor gracias a la secuencia de Maclaurin es suma"
print(f"Se necesitaron {i} iteraciones para el margen de error menor a 0.1%: {porcentaje}") # imprimir "Se necesitaron i iteraciones para el margen de error menor a 0.1%: porcentaje"    
```

## 10. Diseñar una función que permita calcular una aproximación de la función arcotangente alrededor de 0 para cualquier valor x en el rango [-1, 1], utilizando los primeros n términos de la serie de Maclaurin. Nota: use math para traer la función arctan y mostrar la diferencia entre el valor real y la aproximación.

``` math
arctan(x) \approx arctan(x,n) \approx \sum_{i=0}^{n} (-1)^i \frac{x^{2i+1}}{(2i+1)}
```
``` python
from math import atan #importar la función atan(arcotangente) del paquete math
x=float(input("Ingrese un número real entre -1 y 1: ")) # x se inicializa como el flotante de la entrada de teclado 
suma:float=0 # suma se inicializa como 0
arctanreal=atan(x) # arctanreal es igual a atan(x)
flag:bool=True # flag se inicializa como verdadero
i=0 # i se inicializa como 0
def error(suma: float): # función error
    global porcentaje # convertir la variable porcentaje creada y utilizada en la función en una global
    err: float = abs(arctanreal - suma) # err se inicializa como el valor absoluto de arctanreal-suma
    if abs(arctanreal) > 1: # si el valor absoluto de arctanreal es mayor a 1
        err /= abs(arctanreal) # err se actualiza como err/|arctanreal|
    else: # si no
        err *= 100 # err se actualiza err*100
    porcentaje=err # porcentaje es igual a err
    if err <= 0.1: # si err es menor o igual a 0.1
        return True # la función retorna verdadero
    else: # si no
        return False # la función retorna falso
if __name__=="__main__": # función principal
    if x <=1 and x>=-1: # si x es menor o igual que 1 y mayor o igual a -1
        flag=True # flag se actualiza como verdadero
    else: # si no
        flag=False # flag se actualiza como falso
        print("Número no valido") # imprimir "Número no valido"

    while flag: # mientras flag sea verdadero
        c:float=(2*i)+1 # c es igual a 2*i+1
        a=(-1)**i # a es igual a (-1)^i
        b=x**c # b es igual a x^c
        nuevoTermino=a * (b / c) #nuevoTermino es igual a a*(b/c)
        suma += nuevoTermino # suma se actualiza como suma + nuevoTermino
        i += 1 # i se actualiza como i+1
        if error(suma): # si la función error con el argumento suma retorna verdadero
            flag=False # flag se actualiza como falso
            print(f"El valor del arcotangente real es {arctanreal}") # imprimir "El valor del arcotangente real es arctanreal"
            print(f"El valor gracias a la secuencia de Maclaurin es {suma}") # imprimir "El valor gracias a la secuencia de Maclaurin es suma"
            print(f"Se necesitaron {i} iteraciones para el margen de error menor a 0.1%: {porcentaje}") # imprimir "Se necesitaron i iteraciones para el margen de error menor a 0.1%: porcentaje"
            break     
```

<details><summary>Cameo y mención especial</summary><p>
<div align='center'>
<figure> <img src="https://i.postimg.cc/8CvZ9GGy/img.jpg" alt="Defensa Civil" width="400" height="auto"/></br>
<figcaption><b> "Los de claro que arreglaron el internet :D" </b></figcaption></figure>
</div>
</p></details><br>
