# Estructuras Anidadas
### Son numeros primos cuando solo son divisibles entre dos y entre si mismos
```
primo = F
divisor = 2

n = readline(prompt="Ingresa un numero:  ")
numero = as.integer(n)

while( divisor<numero )
{
  if(numero%%divisor == 0)
  {
    primo = !primo
    break
  }
  divisor = divisor + 1
}

if(primo){
  cat(numero, " es primo\n")
}else{
  cat(numero, " NO es primo\n")
}
```
# Ejercicio Entrada a Bar 
### Un cadenero permitira o denegara el acceso a 10 personas
- Con estructuras anidadas hacer un sistema donde de acceso a personas mayores de 18 años
- Se tiene que pedir la edad de la persona
- Debe identificar si es hombre o mujer (recomendacion hombre = 1 y mujer = 2)
- Puede ser automatico el sexo o se puede pedir
```
personas = 0

while (personas < 10)
{
  n = readline(prompt="Edad de la persona:  ")
  edad = as.integer(n)
  sexo = sample(c(1,2), 1)
  if(edad<18)
  {
    if(sexo == 1)
      cat("Acceso Denegado a Hombre de ",edad)
    else
      cat("Acceso denegado a una Mujer de ", edad)
  }else{
    if(sexo == 1)
      cat("Acceso Permitido a Hombre de ",edad)
    else
      cat("Acceso Permitido a una Mujer de ", edad)
  }
    
  personas = personas + 1  
}
```