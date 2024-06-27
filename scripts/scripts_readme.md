"Proyecto Pristimantis galdi"

date: "2024-06-27"
---
### Realizar una filogenia con el gen mitocondriales (16S)para las secuencias obtenidas de Pristimantis galdi de Ecuador y Perú.

# **WGET para Windows**

## 1. Descarga e instalación de wget
Se usó Wget for Windows, se descargó la versión más actualwget.exe:

```
[GNU wget](https://eternallybored.org/misc/wget/)
```

## 2. Movimiento del archivo wget.exe al PATH
Se movió el archivo wget.exe a una carpeta del sistema de mi computador que está en el PATH, como C:\Program Files\wget.

## 3. Adición de la carpeta al PATH: 
a. Búsqueda de la pestaña (Editar variables de entorno) en el buscador del Escritorio.
b. Clic en Variables de Entorno.
c. En la sección Variables del sistema, búsqueda de la variable Path y selecciona Editar.
d. Ingresa la ruta a la carpeta donde se movió wget.exe.
e. Aceptar en todas las ventanas externas para aplicar todos los cambios.

## 4. Verificar la instalación 
Abrir GitBash y escribe el siguiente comando para verificar que wget se ha instalado correctamente y está en el PATH:

```
wget --version
```
Se verá la información sobre la versión de wget instalada, confirmando que la instalación fue exitosa.


# **Musscle para Windows**

## 1. Descarga e instalar iqtree2
Para Windows descargar el archivo exe.
https://github.com/rcedgar/muscle/releases/tag/5.1.0

Luego solo tiene que solo arrastrar el documento a su escritorio. No necesitan instalar este es un archivo ejecutable (i.e listo para correr)

Desde el escritorio donde tienen el archivo galdi2.fasta (ranas) escribir:


```
./muscle5.1.win64.exe -align galdi2.fasta -output musscle_galdi2.aln.fasta

```


# **IQTREE2 para Windows**

## 1. Descargar e instalar iqtree2
Crear una carpeta Iqtree y descarga iqtree2 comprimido zip para Windows.

```
wget https://github.com/iqtree/iqtree2/releases/download/v2.2.0/iqtree-2.2.0-Windows.zip
```

## 2. Descomprimir el archivo iqtree2-2.0-Windows.zip

```
unzip iqtree-2.2.0-Windows.zip
```

## 3. Mover el archivo descomprimido al PATH:
Mover el archivo descomprimido a C:\Program Files\Iqtree. 

## 4. Agregar la carpeta al PATH:
a. Busca "Editar variables de entorno" en el buscador de la barra inferior del Escritorio.
b. Haz clic en Variables de Entorno.
c. En la sección Variables del sistema, busca la variable Path y selecciona Editar.
d. Haz clic en Nuevo e ingresa la ruta a la carpeta Iqtree y a la subcarpeta del archivo       ejecutable, por ejemplo, C:\Program Files\Iqtree\bin
e. Haz clic en Aceptar en todas las ventanas abiertas para aplicar los cambios.

## 3. Verificar la instalación:
Abre GitBash y escribe el siguiente comando para verificar que IQ-TREE se ha instalado correctamente y está en el PATH:

```
iqtree2 -h
```
Este comando debe mostrar la ayuda de IQ-TREE, confirmando que la instalación ha sido exitosa.


# **Análisis Filogenético**


## 1. Correr archivo alineado con IQ-TREE

a. En el caso de tener un archivo fasta alineado (concantenado con todos los genes) y un archivo con la particion usar el siguiente script:

```
iqtree2 -s musscle_galdi2.aln.fasta -B 1000
```

```
c. Se generan varios archivos y escoger entre ellos, "musscle_galdi2.aln.fasta.treefile".

```
musscle_galdi2.aln.fasta.treefile
```

d. Visualizar el archivo con el programa FigTree. 
