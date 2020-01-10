# Funciones

## Funcion sin return
```
funcion1 = function(argumento)
{
  argumento = argumento + 2
  # Funcion sin return explicito
  # salida = argumento + 2
  # salida
}
```
```
vector = 1:20
vectorRes = funcion1(vector)
print(vector)
print(vectorRes)
```
## Funcion con return
```
funcion2 = function(argumento)
{
  suma = sum(argumento)
  return(suma)
}

res = funcion2(vector)
print(res)
```
# Ejercicio Funcion que saca area de un rectangulo y volumen de un prisma rectangular segun lo que quiera el usuario
- Si el usuario da 1 sacara el area y debe proporcionar ancho y altura
- Si el usuario da 2 sacara el volumen y debe proporcionar ancho, altura y profundidad
```
# Funcion Area 
# Recibe ancho y altura
# Return implicito
areaRec = function(ancho,altura)
{
  area = ancho * altura
  area
}

# Funcion Volumen
# Recibe ancho,altura,profundidad
# return implicito
volumenRec = function(ancho,altura,profundidad)
{
  volumen = ancho * altura * profundidad
  volumen
}

# Funcion principal (main)
# Dependiendo si el usuario da 1 o 2 llama a la funcion de area o volumen
# Return Explicito: Regresa el area o volumen
AreaVolumen = function()
{
  print("Calculo de Area y Volumen")
  print("1 = Area   2 = Volumen")
  opc = readline(prompt="Ingresa un numero:  ")
  numero = as.integer(opc)
  
  if(opc == 1)
  {
    n = readline(prompt="Ancho:  ")
    anchura = as.integer(n)
    n = readline(prompt="Altura:  ")
    altura = as.integer(n)
    area = areaRec(ancho = anchura,altura)
    return(area)
  }
  if(opc == 2)
  {
    n = readline(prompt="Ancho:  ")
    anchura = as.integer(n)
    n = readline(prompt="Altura:  ")
    altura = as.integer(n)
    n = readline(prompt="Profundidad:  ")
    profundidad = as.integer(n)
    volumen = volumenRec(anchura,altura,profundidad)
    return(volumen)
  }
}

# Usando nuestras funciones
res = AreaVolumen()
print(res)
```