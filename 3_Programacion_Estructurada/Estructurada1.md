# Ejercicios simples de los operadores relacionales
```
print(10!=9 )
```
# Ejercicios simples de los operadores logicos
```
print(10!=9 & 5>9 )
```
# If
```
if(TRUE)
{
  print("Es TRUE")
}

if(FALSE)
{
  print("Es TRUE")
}
```
```
n = readline(prompt="Dame el total de inscritos: ")
num = as.integer(n)

if(num>50)
{
  print("El numero de inscritos excedio el limite de 50")
}
```
# If-else
```
n = readline(prompt="Dame el total de inscritos: ")
num = as.integer(n)

if(num>50)
{
  print("El numero de inscritos excedio el limite de 50")
} else {
  print("Aun hay cupo en el salon")  
}
```
```
calificaciones = c(6, 7, 8, 9, 8)  
media = mean(calificaciones)

if(media >= 6) {
  cat("Calificacion: ", media, " \nAprobado\n")
} else {
  cat("Calificacion: ", media, " \nReprobado\n")
}
```
```
n = readline(prompt="Dame un numero: ")
num = as.integer(n)

if(num < 0)
{
  print("El numero es negativo")
} else if(num == 0 ) {
  print("El numero es 0")
} else {
  print("El numero es positivo")
}
```
# Ejercicio Acceso a Parque de Diversiones General
### No se acepta numero negativo y edad 100 o mas
- edad < 12: Area de Niños
- edad 12 - 18: Area de Jovenes
- edad 18 - 65: Area de Adultos
- edad > 65: Area de la Tercera Edad
```
n = readline(prompt="Ingrese edad: ")
edad = as.integer(n)

if(edad < 0)
{
  print("Edad Invalida")
} else if(edad < 12){
  print("Tiene Acceso al Area de Niños")
} else if (edad >= 12 & edad < 18){
  print("Tiene Acceso al Area de Jovenes")
} else if (edad >=18 & edad < 65) {
  print("Tiene Acceso al Area de Adultos")
} else if (edad >= 65 & edad < 100) {
  print("Tiene Acceso al Area de la Tercera Edad")
} else {
  print("No se aceptan edades mayor a 100 años")
}
```