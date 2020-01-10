# XLSX
- [RTools](https://cran.r-project.org/bin/windows/Rtools/)  Acceder e instalar en caso de un Warning de que falta Rtools a la hora de instalar cualquier paquete (Instalen el de Color Verde)

## Paquete xlsx
```
install.packages("xlsx")
library("xlsx")
#dado1 = read.xlsx2("Excel/Dados.xlsx","1Dado")
dado1 = read.xlsx2("Excel/Dados.xlsx","1Dado")
head(dado1)
class(dado1)
```
```
dado15 = read.xlsx2(file.choose(),3)
head(dado15)
class(dado15$Dado1)
```
# Paquete readxl
```
install.packages("readxl")
library("readxl")

dado1 = read_excel("Excel/Dados.xlsx")
head(dado1)
class(dado1$Dado1)
```
```
dado2 = read_excel("Excel/Dados.xlsx", sheet = 2)
head(dado2)
```
```
# Archivo Dados
dado30 = read_excel(file.choose(), sheet = 4)
head(dado30)

dado1 = read_excel("Excel/Dados.xlsx", col_names = F)
head(dado1)

dado1 = read_excel("Excel/Dados.xlsx", sheet = 4, skip = 5)
head(dado1)
```