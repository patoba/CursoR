# Web
- [CSVs Online](https://people.sc.fsu.edu/~jburkardt/data/csv/csv.html)
```
casas = read.csv("https://people.sc.fsu.edu/~jburkardt/data/csv/homes.csv",  strip.white = T)
head(casas)
tail(casas)
Indices =  casas$Rooms < 8 & casas$Taxes < 3000
print(Indices)
misOpc = casas[Indices,]
print(misOpc)
```

# Ejercicio
### Arboles con circunferencia mayor a 15 ,peso mayor a 70 y volumen mayor a 55
```
arboles = read.csv("https://people.sc.fsu.edu/~jburkardt/data/csv/trees.csv")
head(arboles)
arbolitos = arboles[arboles$Girth..in. > 15 & arboles$Height..ft. > 70 & arboles$Volume.ft.3. > 55,] # Falta agregar la coma en clase al final, ya que es un data Frame para agregar toda la columna y NADIE me dijo xD
print(arbolitos)
```

# Ejemplo Real (Intervalos de Confianza para la Media)
### Datos: Interesados al taller de Arduino-Processing (Semana Soft-Hard Vol.II)
```
# Importando
poblacion = read.csv("CSV/Registro Semana Soft-Hard (Respuestas).csv") 
# Indices del muestreo aleatorio simple
indices_muestra = c(2,3,20,17,8,6,7,12,10,28)
# Guardando la columna de los que se registraron en el taller de Processing
# 1: Registrado
# 0: No registrado
muestra = poblacion[indices_muestra,6]

# Datos de la muestra
n = length(indices_muestra) # Longitud de la muestra
X = mean(muestra) # Promedio de los registrados
vari = var(muestra) # Varianza de los registrados

# n < 30
# Distribucion de T-student 
# IC: 95%
# t 0.025,9
t = 2.262

# Calculando los intervalos de confianza
U = X - (t * (vari/sqrt(n)))
L = X + (t * (vari/sqrt(n)))

cat("Intervalo de Confianza para la media","\nLimite Inferior: ",U,"\nLimite Superior: ",L)
```