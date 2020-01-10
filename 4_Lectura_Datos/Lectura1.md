# CSV 
- Recomendacion : No correr el Script con Source si no con Ctrl+Enter linea por linea 
- No se les olvide usar setwd() para posicionarse en su carpeta y no poner toda la ruta de los archivos
```
# Archivo sin Header
csv = read.csv("CSV/prueba1.csv")
class(csv)
head(csv)
head(csv$juanazo.fi.gmail.com)

csv = read.csv("prueba1.csv",header = F)
head(csv)
head(csv$V3)
```
```
# Archivo con Header prueba2.csv
csv = read.csv(file.choose())
head(csv)
head(csv$Nombre.Completo)

ruta = file.choose()
print(ruta)

# Diciendo que prueba2.csv no tiene Headers
csv = read.csv(file.choose(), header = F)
head(csv)
head(csv$V1)
```
```
# Archivo con Headers engañosos prueba3.csv
csv = read.csv(file.choose())

csv = read.csv(file.choose(),skip = 4)
head(csv)
head(csv$Nombre.Completo)
```
```
# CSV separador decimal ; Archivo Letras
csv2 = read.csv2(file.choose())
class(csv2)
print(csv2)

csv2 = read.csv2(file.choose(), header = F)
print(csv2)
```
```
# CSV separador por tabulador /t Archivo Nilo
delim = read.delim(file.choose())
print(delim)
```
```
# Ejemplo stringAsFactors Archivo grades
calif = read.csv(file.choose())
print(calif)
class(calif$First.name)

calif = read.csv(file.choose(),stringsAsFactors = F)
print(calif)
class(calif$First.name)
```