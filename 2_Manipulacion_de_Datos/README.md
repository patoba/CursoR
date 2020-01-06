Manipulación de Datos
=====================

Objetivo
--------

Entender los tipos de datos básicos que R posee

Indice
------

**[1. Conceptos Clave][1]**  
**[2. Vectores][2]**  
**[3. Matrices][3]**  
**[4. Arreglos][4]**  
**[5. DataFrames][5]**  
**[Retorno][6]**  

### 1. Conceptos Clave

#### Logical

***Logical** es un tipo de dato que almacena unicamente T ó F. Podemos encontrar en R constantes True y False como TRUE y FALSE  o como T y F. Al aplicar ciertos operadores el resultado es un valor de tipo Logical este es el caso de los operadores de comparación (>, <, !=, ==, <=, >=) y los operadores relacionales (!, & |)

```
1 == 3  # Regresa F
1 == 1  # Regresa T
T & T # Regresa T
```

Otro ejemplo:

```
a <- 4
b <- 5
a != b  # Regresa T
```

#### Integer

El tipo de dato **Integer** permite almacenar enteros ya sea positvos o negativos

```
a <- 4
a + 3  # Regresa 7
```

#### Double

El tipo de dato **Double** permite trabajar con numeros reales

```
a <- 4.5
b <- 6
a + b  # 10.4
```

Algunas funciones utiles cuando trabajamos con números en R

```
x <- 3.475
abs(x)  # Valor absoluto. Salida = 3.475
sqrt(x)	 # Raiz cuadrada. Salida = 1.864135
ceiling(x)  # Redondeo hacia arriba. Salida = 4
floor(x)  # Redondeo hacia abajo. Salida = 3
trunc(x)  # Quita los decimales. Salida = 3
round(x, digits=2)  # Redondeo a dos decimales. Salida = 3.48
round(x)  # Redondeo usual. Salida = 3
cos(x)  # Funcion coseno. Salida = -0.9449327
sin(x)  # Funcion seno. Salida = -0.3272646
tan(x)  # Funcion tangente. Salida = 0.3463364
log(x)  # Logaritmo natural. Salida = 1.245594
log10(x) # Logaritmo base 10. Salida = 0.5409548
exp(x)  # Exponencial. e^x. Salida = 32.29783
```
#### Complex

El tipo de dato **Complex** permite trabajar con números complejos. 

```
z <- 5-2i
z * z  # La salida es 21-20i
```

Funciones imporantes relacionadas con complejos 

```
x <- 1+sqrt(3)/2i
Re(x)  # Parte real. Salida = 1
Im(x)  # Parte Imaginaria. Salida = -0.8660254
Mod(x)  # Modulo. Salida = 1.322876
Arg(x)  # Argumento. Salida = -0.7137244
Conj(x)  # Conjugado. Salida = 1+0.866025i
```

#### Character

El tipo de dato **Character** permite representar cadenas (textos) en R. Deben estar entre comillas simples ('') o dobles ("").

```
cadena1 <- 'cadena'
cadena2 <- 'cadena'
```

Funciones Importantes Relacionadas con Character

```
paste(c("asd", "sd"), collapse = "")  # Permite concatenar un vector de Characters. Salida = "asdsd"
toupper('asd')  # Convierte todo a mayusculas. Salida = 'ASD'
tolower('ASd')  # Convierte todo a minusculas. Salida = 'ASd'
unlist(strsplit("asd%asd", split="%"))  # Separa la cadena por un caracter. Salida = c('asd', 'asd')
```

La variable LETTERS cargada por defecto en R posee todas las letras del alfabeto
### 2. Vectores

Un **vector** es un tipo de dato que posee multiples elementos del mismo tipo. Se pueden crear vectores de elementos que sean Logical, Integer, Double, Complex, Character.

#### Creación

La forma mas sencilla de crear un vector es la siguente:

```
v <- c(1,2,3)
```

donde v contiene 3 elementos numericos. Tambien es posible crearlo de las siguientes formas:

```
v1 <- c(1+2i, 0+4i)
v2 <- 1:5  # equivalente a c(1, 2, 3, 4, 5)
v3 <- seq(1, 4, by = 2)  # Equivalente a c(1, 3)
v4 <- rep(1:3, 4)  # Equivalente a c(1, 2, 3, 1, 2, 3, 1, 2, 3, 1, 2, 3)
v5 <- c(v2, v3)  # Equivalente a c(1, 2, 3, 4, 5, 1, 3)
```

##### Funciones Importantes de Vectores

Existen funciones interesantes relacionadas con vectores

```
v <- 2:6
summary(v)  # Muestra primer cuantial
length(v)  # Regresa el tamaño del vector. Salida = 5
head(v)  # Regresa los primeros elementos del vector. Salida = 2 3 4 5 6
tail(v)  # Regresa los ultimos elementos del vector. Salida = 2 3 4 5 6
mean(v)  # Regresa la media del vector. Salida = 4
max(v)  # Regresa el elemento máximo del vector. Salida = 6
median(v)  # Regresa la mediana del vector. Salida = 4
sum(v)  # Regresa la suma de todos los elementos del vector. Salida = 20
prod(v)  # Regresa el producto de todos los elementos del vector. Salida = 720 
abs(v)  # Regresa un vector que aplica el valor absoluto a cada elemento del vector.
```

##### Indexación

Podemos acceder a elementos de un vector de diversas formas. La forma mas sencilla es con sus indices.

```
x <- 101:200
x[1]  # Accedemos al elemento con indice 1 es decir el primero, nos regresa 100
x[c(2, 5)]  # Accedemos a los elementos con indice 2, y 5. Nos regresa 202, 205
x[1:50]  # Accedemos a los elementos con indices del 1 al 50. Nos regresa 201 y 259
```

Otra forma de acceder a elementos es con un vector logical. Este vector logical debe tener un tamaño menor y multiplo que del tamaño del vector al que queremos acceder sus elementos.

```
v <- 1:10
menores_a_10 <- v <= 5
menores_a_10  # Posee T, T, T, T, T, F, F, F, F, F
v[menores_a_diez]  # Nos da 1, 2, 3, 4, 5
```

Hay veces que queremos evitar ciertos valores esto lo logramos usando indices negativos. El indice negativo quita dicho elemento del vector

```
v <- 1:4
v[-1] # Nos da 1, 2, 3
v[-c(1,2)] # Nos da 1, 2
```

#### Ordenaciones

Si tenemos un vector existen ocasiones en las que queremos ordenarlos o invertir el orden de sus elementos

```
v <- c(2, 1, 0, 4)
sort(v)  # Ordena los elementos del vector. Nos regresa 0 1 2 4
order(v)  # Nos regresa los indices que cada elemento ocuparia si el vector estuviera ordenado. Nos regresa 3 2 1 4
v[order(v)] # Nos regresa 0 1 2 4
sort(v) == v[order(v)]  # Nos regresa TRUE
rev(v)  # Invierte el orden. Nos regresa 4 0 1 2
```

#### All, Any, %in%

Existen funciones que nos regresan un Logical si encuentran determinadas caracteristicas en un vector, all regresa T si todos los elementos del vector son T, en cualquier otro caso regresa F. Any regresa T si por lo menos un elemento del vector es T, en cualquier otro caso regresa F.

```
v1 <- c(T, T)
v2 <- c(T, F)
v3 <- c(F, F)
all(v1)  # Regresa TRUE
all(v2)  # Regresa FALSE
all(v3)  # Regresa FALSE
any(v1)  # Regresa TRUE
any(v2)  # Regresa TRUE
any(v3)  # Regresa FALSE
```

%in% es un operador que determina si un determinado valor se encuentra como elemento de un vector

```
c <- 'a'
v <- c('a', 'b', 'c')
c %in% v  # Regresa T
```

#### Operaciones

Se pueden realizar operaciones con una variable y un vector

```
v1 <- c(1,2,3,4)
c <- 3
v1 * c  # Da como resultado 3, 6, 9, 4
v1 + c  # Da como resultado 4, 5, 6, 7 
v1 / c  # Da como resultado 0.3333333, 0.6666667, 1.0000000, 1.3333333
v1 - c  # Da como resultado -2, -1, 0, 1
```

Se pueden realizar operaciones entre dos vectores del mismo tamaño

```
v1 <- c(1,2,3,4)
v2 <- c(5, 6, 7, 8)
v1 * v2  # Da como resultado 5, 12, 21, 32
v1 + v2 # Da como resultado 6, 8, 10, 12
v1 / v2  # Da como resultado 0.2000000, 0.3333333, 0.4285714, 0.5000000
v1 - v2  # Da como resultado -4, -4, -4, -4
```

Se pueden realizar operaciones entre vectores con distinto tamaño siempre y cuando el tamaño de un vector debe ser multiplo del otro

```
v1 <- c(1, 2, 3, 4)
v2 <- c(5, 6)
v1 * v2  # Da como resultado 5 12 15 24
v1 + v2  # Da como resultado 6  8  8 10
v1 - v2  # Da como resultado -4 -4 -2 -2
v1 / v2  # Da como resultado 0.2000000 0.3333333 0.6000000 0.6666667
v1 %% v2  # Da como resultado 1 2 3 4
```

### 3. Matrices

### 4. Arreglos

### 5. DataFrames

### Retorno


[1]: https://github.com/patoba/CursoR/tree/master/1_Introduccion_a_R '1. Conceptos Clave'
[2]: https://github.com/patoba/CursoR/tree/master/2_Manipulacion_de_Datos '2. Vectores'
[3]: https://github.com/patoba/CursoR/tree/master/3_Programacion_Estructurada '3. Matrices'
[4]: https://github.com/patoba/CursoR/tree/master/4_Lectura_Datos '4. Arreglos'
[5]: https://github.com/patoba/CursoR/tree/master/5_Graficacion '5. DataFrames'
[6]: https://github.com/patoba/CursoR '6. Retorno'
