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

**Logical** es un tipo de dato que almacena unicamente T ó F. Podemos encontrar en R constantes True y False como TRUE y FALSE  o como T y F. Al aplicar ciertos operadores el resultado es un valor de tipo Logical este es el caso de los operadores de comparación (>, <, !=, ==, <=, >=) y los operadores relacionales (!, & |)

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

Una **matriz** es un conjunto de objetos del mismo tipo ordenados por columnas y filas. 

#### Creación

Para crear una matriz se usa la función matrix(data = NA, nrow = 1, ncol = 1, byrow = FALSE,
                                            dimnames = NULL)  

donde:
> **data:** Son los elementos de la matriz
> **nrow:** Número de renglones
> **ncol:** Número de columnas
> **byrow:** Ir insertando data por renglones
> **dinmames:** Nombre a columna/filas

Ejemplos:

```
matrix(1:10)

Salida:
 [,1]
 [1,]    1
 [2,]    2
 [3,]    3
 [4,]    4
 [5,]    5
 [6,]    6
 [7,]    7
 [8,]    8
 [9,]    9
[10,]   10
```

```
matrix(1:10, nrow=2)

Salida:
     [,1] [,2] [,3] [,4] [,5]
[1,]    1    3    5    7    9
[2,]    2    4    6    8   10
```

```
matrix(1:10, ncol = 2)

Salida:
     [,1] [,2]
[1,]    1    6
[2,]    2    7
[3,]    3    8
[4,]    4    9
[5,]    5   10
```

```
matrix(1:10, ncol = 2, byrow=T)

Salida:
     [,1] [,2]
[1,]    1    2
[2,]    3    4
[3,]    5    6
[4,]    7    8
[5,]    9   10
```

marca error
```
matrix(1:10, 3, 3)
```

#### Funciones Asociadas a una Matriz

Algunas funciones utiles al trabajar con matrices

```
m <- matrix(1:6, ncol=2, byrow=T)

dim(m)  # Dimensiones de la matriz. Salida = 3 2
dimnames(m)  # Nombre de las dimensiones de la matriz. Salida = NULL
colnames(m)  # Nombre de las columnas de la matriz. Salida = NULL
rownames(m)  # Nombre de los renglones de la matriz. Salida = NULL
mode(m)  # Tipo de datos de la matriz. Salida = "numeric"
length(m)  # Devuelve el total de elementos de la matriz. Salida = 6
is.matrix(m)  # Devuelve T si m es una matriz. Salida = T
```

Cambiando el nombre a las columnas y renglones

```
m <- matrix(1:6, ncol=2, byrow=T)
colnames(m) <- c('a', 'b')
rownames(m) <- tolower(rev(LETTERS)[1:3])
colnames(m)  # Salida = 'a' 'b'
rownames(m)  # Salida = "z" "y" "x"
```

Cargando los colnames y rownames en la creacion

```
col <- c('a', 'b')
row <- tolower(rev(LETTERS)[1:3])
m <- matrix(1:6, ncol=2, byrow=T, dimnames = list(row, col))
colnames(m)  # Salida = 'a' 'b'
rownames(m)  # Salida = "z" "y" "x"
```

#### Concatenar Datos

Podemos concatenar agregar una nueva columna o fila con las funciones cbind y rbind  

Agregando una columna:

```
m <- matrix(1:4, nrow=2)
v <- 11:12
cbind(m, v)

Salida:
          v
[1,] 1 3 11
[2,] 2 4 12
```

Agregando un renglon:

```
m <- matrix(1:4, nrow=2)
v <- 11:12
rbind(m, v)

Salida:
  [,1] [,2]
     1    3
     2    4
v   11   12
```

#### Acceder a Elementos

Podemos acceder a elementos de la matriz de diversas formas

Elemento 1,2 de la matriz m

```
m <- matrix(1:4, nrow=2)
print(m[1,2])  # La salida es 3
```

Toda la segunda columna

```
m <- matrix(1:4, nrow=2)
print(m[,2])  # La salida es 3 4
```

Toda la primera fila

```
m <- matrix(1:4, nrow=2)
print(m[1,])  # La salida es 1 3
```

#### Función Apply

Podemos aplicar una función sobre los renglones o columnas. Aplicaremos la función apply sobre las columnas de una matriz.

```
m <- matrix(1:6, nrow = 3)
apply(m, 2, max)  # Obtenemos el maximo de cada columna. El 2 simboliza el maximo
                  # Salida = 3 6
```

#### Operaciones con Matrices

Las matrices poseen operaciones basicas entre ellas, con vectores y con escalares

```
m1 <- matrix(1:4, nrow = 2)
m2 <- matrix(5:8, nrow = 2)

m1 + m2  # Suma
m1 - m2  # Resta
m1 * m2  # Multiplicacion (elemento a elemento)
m1 / m2  # Division (elemento a elemento)
```

Operaciones Matriz - Vector. El vector se convierte en una matriz que posee las dimensiones de la matriz con la que queremos realizar la operación.

```
m <- matrix(1:4, nrow = 2)
v <- c(5, 6)

m + v  # Suma
m - v  # Resta
m * v  # Multiplicación
m / v  # División
```

Operaciones Matriz - Escalar. Se crea una matriz que posee una dimensión igual a la matriz con la que queremos realizar la operación que todos sus elementos son el escalar

```
m <- matrix(1:4, nrow = 2)
c <- 10

m + c  # Suma
m - c  # Resta
m * c  # Multiplicación
m / c  # División
```

#### Funciones de Algebra Lineal

Existen multiples funciones/operadores relacionados con Algebra Lineal en R

Multiplicación usual de matrices

```
m1 <- matrix(1:4, nrow = 2)
m2 <- matrix(5:8, nrow = 2)

m1 %*% m2  # Multiplicación usual de matrices
```

```
m <- matrix(1:4, nrow = 2)
v <- c(5, 6)

m %*% v  # Multiplicación usual de matrices. El vector se trabaja como un vector columna.
```

Transpuesta de una matriz

```
m <- matrix(1:4, nrow = 2)
t(m)  # Transpuesta de una matriz
```

Vector unitario

```
matrix(0, 10, 1)
```

Diagonal de una matriz

```
m <- matrix(1:4, nrow = 2)
diag(m)  # 1 4
```

Matriz diagonal

```
v <- 1:3
diag(v)
```

Matriz Identendidad

```
diag(rep(1, 3))
```

Inversa de una Matriz

```
m <- matrix(1:4, nrow=2)
solve(m)  # Inversa
```

Determinante de una matriz

```
m <- matrix(1:4, nrow=2)
det(m)  # La matriz debe ser cuadrada no singular
```

### 4. Arreglos

Los arreglos son estructuras multidimensionales pueden poseer mas de dos dimensiones

a <- array(1:12 * 3,
            dim = c(2,3,2),  # Renglones, columnas, altura
            dimnames = list(c("hombres","mujeres"),c("edad","peso","altura"),
                            c("villarriba","villabajo")))

#### Accediendo a elementos

Todos los elementos de la ciudad villabajo

```
a[,,"villabajo"]

Salida:
edad peso altura
hombres   21   27     33
mujeres   24   30     36
```

#### Funcion apply

Promedio de altura, peso y altura de hombres y mujeres 

```
apply(a,2,mean)

Salida:

```
### 5. Listas

Las listas son estruturas que permiten almacenar elementos de distintos tipos de datos

#### Creación

Una lista se puede crear de la forma

```
lista <- list("cadena1", "cadena2", 5:3, T, 229.21)

Salida:
[[1]]
[1] "cadena1"

[[2]]
[1] "cadena2"

[[3]]
[1] 5 4 3

[[4]]
[1] TRUE

[[5]]
[1] 229.21
```

Podemos crear una lista cuyos elementos tengan una etiqueta, lo podemos hacer de la siguiente forma:

```
lista <- list(1:3, matrix(c(1:4), nrow = 2),
        list("azul", 5.9))  # Creamos la lista
names(lista) <- c("primer", "segundo", "tercero")
print(lista)

Salida:
$primer
[1] 1 2 3

$segundo
     [,1] [,2]
[1,]    1    3
[2,]    2    4

$tercero
$tercero[[1]]
[1] "azul"

$tercero[[2]]
[1] 5.9
```
#### Accediendo a elementos de una lista

Accediendo a elementos de una lista por indices

```
lista <- list(1:3, matrix(c(1:4), nrow = 2),
        list("azul", 5.9))  # Creamos la lista
names(lista) <- c("primer", "segundo", "tercero")

print(lista[1])  # Accedemos al primer elemento de la lista

Salida:
1 2 3
```

Accediendo a elementos de una lista por nombres

```
lista <- list(1:3, matrix(c(1:4), nrow = 2),
        list("azul", 5.9))  # Creamos la lista
names(lista) <- c("primer", "segundo", "tercero")

print(lista$segundo)  # Accedemos al primer elemento de la lista

Salida:
a
     [,1] [,2]
[1,]    1    3
[2,]    2    4
```

Accediendo a elementos de elementos de una lista

```
lista <- list(1:3, matrix(c(1:4), nrow = 2),
        list("azul", 5.9))  # Creamos la lista
names(lista) <- c("primer", "segundo", "tercero")

print(lista[3][1])  # Accedemos al primer elemento del tercer elemento de la lista 

Salida:
5.9
```
#### Convertir una lista a un vector

Para convertir una lista a un vector se usa la función unlist

```
lista <- list(LETTERS)
print(unlist(LETTERS))

Salida:
[1] "A" "B" "C" "D" "E" "F" "G" "H" "I" "J" "K" "L" "M" "N" "O" "P" "Q" "R" "S"
[20] "T" "U" "V" "W" "X" "Y" "Z"

```

```
lista <- list(LETTERS, 1:20)
unlist(lista)

Salida:
 [1] "A"  "B"  "C"  "D"  "E"  "F"  "G"  "H"  "I"  "J"  "K"  "L"  "M"  "N"  "O" 
[16] "P"  "Q"  "R"  "S"  "T"  "U"  "V"  "W"  "X"  "Y"  "Z"  "1"  "2"  "3"  "4" 
[31] "5"  "6"  "7"  "8"  "9"  "10" "11" "12" "13" "14" "15" "16" "17" "18" "19"
[46] "20"
```

### 6. DataFrames



[1]: https://github.com/patoba/CursoR/tree/master/2_Manipulacion_de_Datos#1-conceptos-clave '1. Conceptos Clave'
[2]: https://github.com/patoba/CursoR/tree/master/2_Manipulacion_de_Datos#2-vectores '2. Vectores'
[3]: https://github.com/patoba/CursoR/tree/master/2_Manipulacion_de_Datos#3-matrices '3. Matrices'
[4]: https://github.com/patoba/CursoR/tree/master/2_Manipulacion_de_Datos#4-arreglos '4. Arreglos'
[5]: https://github.com/patoba/CursoR/tree/master/2_Manipulacion_de_Datos#5-dataframes '5. DataFrames'
[6]: https://github.com/patoba/CursoR '6. Retorno'
