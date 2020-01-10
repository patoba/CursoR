# For
```
for (i in 1:10)
  print(i)
```
## Para acceder de forma secuencial a los distintos valores de un vector, matriz o data.frame se pueden usar códigos como el siguiente:
```
perros <- c("cucho", "bobi", "morti", "sultan", "fido", "yonofui")

for (i in 1:length(perros)) 
  print(paste("Mi perro se llamaba:", perros[i]))
```
# Promedio de una matriz
```
vector1 = c(1,2,3,4)
vector2 = c(5,6,7,8)
vector3 = c(9,10,11,12)
# rbind
m = rbind(vector1,vector2,vector3) # Unimos por renglones
for (i in 1:nrow(m)) 
  print(mean(m[i, ]))
```
# La caminata del borracho 
### Es un proceso muy simple: en cada iteración se tira una moneda (usaremos "sample" para esto) y el borracho se mueve un paso a la izquierda o a la derecha según el caso.

### Hagamos un borracho con 50 iteraciones, cuya posición inicial es el cero.
```
posicion = numeric(50) # vector de 50 iniciado en ceros
for (i in 1:49) 
{
  paso = sample(c(-1, 1), 1) # sample arrojara un valor del vector que contiene del -1 a 1
  posicion[i + 1] = posicion[i] + paso # se guarda la posicion del borracho
  
}

print(posicion) # se imprime la posision del borracho
```

# Ejercicio For
### Encontrar el numero maximo y minimo de un vector de 10 numeros del 0 - 100 con un for
```
vec = c(8,2,23,2,4,7,8,5,4,22)
max = 0
min = 1000

for(x in vec)
{
  if(max<x)
    max = x
  if(min>x)
    min = x
}

cat("Maximo:" ,max)
cat("\nMinimo:",min)
print(min(vec))
print(max(vec))
```