# While
```
fin = 5
valor = 0

while(valor < fin) {
  print("Todavía no.")
  valor = valor + 1
}
print ("Ya llegaste")
```

# Ciclo infinito
```
inicio = 0
fin = 5

while(inicio < fin) {
  print("Presiona ESC para detener")
}
```
# Ejercicio
### Pedir el radio del circulo y mientras el radio sea cero o menor a cero se pedira nuevamente un radio valido una vez con el radio valido, sacar el area del circulo
```
n = readline(prompt="Favor de digitar el radio:  ")
radio = as.double(n)

while(radio <= 0)
{
  print("El radio debe ser mayor de 0")
  n = readline(prompt="Favor de digitar de nuevo el radio:  ")
  radio = as.double(n)
}

cat("El area del circulo es ",(radio^2)*pi)
```