# Vectorizacion
## Ejemplo Valor Absoluto de un vector
```
# Por ciclos (Sin Vectorizar)
cicloAbs = function(vector)
{
  for( i in 1:length(vector))
  {
    if(vector[i] < 0)
    {
      vector[i] = -vector[i]
    }
  }
  return(vector)
}

# Vectorizada
vecAbs = function(vector)
{
  negativos = vector < 0
  vector[negativos] = vector[negativos] * -1
  return(vector)
}

# Vector de 500000 elementos con -1 o 1
vectorPrueba = rep(c(-1,1), 5000000)

inicio = Sys.time() # Sacamos tiempo inicio
nuevoVecC = cicloAbs(vectorPrueba)
fin = Sys.time() # Sacamos tiempo final
print("Tiempo Ciclo: ")
print(fin-inicio) # Imprimimos cuanto se tardo
#print(nuevoVecC)

inicio = Sys.time() # Sacamos tiempo inicio
nuevoVecV = vecAbs(vectorPrueba)
fin = Sys.time() # Sacamos tiempo final
print("Tiempo vectorizada: ")
print(fin-inicio) # Imprimimos cuanto se tardo
#print(nuevoVecV)
```

## Gregory-Leibniz
```
sinVectorizar = function (limite)
{
  p = 0
  for (n in limite:0) {
    p = (-1)^n/(2 * n + 1) + p
  }
  return(p)
}


Vectorizada=function (limite)
{
  n = seq(1, limite, by = 4)
  #print(n)
  p = sum(1/n-1/(n + 2))
  return(p)
}

inicio = Sys.time()
p = sinVectorizar(100000)
fin = Sys.time()
print(fin-inicio)

inicio = Sys.time()
a = Vectorizada(100000)
fin = Sys.time()
print(fin-inicio)

s = pi/4
```