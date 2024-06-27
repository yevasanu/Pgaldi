"Proyecto Pristimantis galdi"

date: "2024-06-27"
---
### Para realizar una filogenia con el gen mitocondrial (16S) de individuos de Pristimantis galdi de Ecuador y Perú.


# **WGET para Windows**

## 1. Descarga e instalación de wget
Se usó Wget for Windows, se para ello se descargó la versión más actualizada wget.exe:

```
[GNU wget](https://eternallybored.org/misc/wget/)
```

## 2. Movimiento del archivo wget.exe al PATH

Se movió el archivo wget.exe a una carpeta del sistema del computador que está en el PATH como C:\... Files\wget.

## 3. Adición de la carpeta al PATH:

Este paso se lo realiza de la siguiente manera:

a. Búsqueda de la pestaña (Editar variables de entorno) en el buscador del Escritorio.
b. Clic en la pestaña "Variables de Entorno".
c. En la sección Variables del sistema, se busca la variable Path y se selecciona la pestaña Editar.
d. Se ingresa la ruta a la carpeta donde se movió wget.exe.
e. Se hace clic en la pestaña Aceptar en todas las ventanas externas para aplicar todos los cambios.

## 4. Verificación de la instalación 

En la terminal GitBash se escribe el comando "wget --version" para verificar que este se haya instalado correctamente y está en el PATH:

```
wget --version
```

Se visualizará la información sobre la versión de wget instalada, confirmando que la instalación fue un éxito.


# **Musscle para Windows**

## 1. Descarga e instalación de Iq-Tree2

Para realizar la descarga del archivo exe para Windows, se usa el siguiente enlace:

https://github.com/rcedgar/muscle/releases/tag/5.1.0

Posterior a ello, se arrastra el documento al escritorio. Como nota: no necesita instalar el archivo ya que es ejecutable y está listo para usarse.

En la terminal Gitbash, se busca donde se tiene el archivo el archivo galdi2.fasta (ranas), se coloca el siguiente comando:

```
./muscle5.1.win64.exe -align galdi2.fasta -output musscle_galdi2.aln.fasta

```
Se corre y sale un mensaje de que fue exitoso cuando está correcto, caso contrario si salen errores se tiene que revisar las secuencias y volver a este paso. 


# **IQTREE2 para Windows**

## Descarga e instalación iqtree2

Para Windows, se crea una carpeta Iqtree y se descarga iqtree2 comprimido zip.

```
wget https://github.com/iqtree/iqtree2/releases/download/v2.2.0/iqtree-2.2.0-Windows.zip
```

## Descompresión del archivo iqtree2-2.0-Windows.zip
Con el siguiente comando se descomprime el archivo Iq.tree, esto se lo hace en la terminal de Gitbash.

```
unzip iqtree-2.2.0-Windows.zip
```
Este archivo descomprimido se mueve a la carpeta C:\Program Files\Iqtree, previamente creada. 

## Adición de carpeta al PATH

Es importante adiccionar está carpeta al path, para lo cual:

a. Se busca "Editar variables de entorno" en la barra inferior del Escritorio.
b. Se hace clic en la pestaña "Variables de Entorno".
c. En la sección Variables del sistema, se busca la variable Path y se selecciona la pestaña Editar.
d. Se hace clic en "Nuevo" y se ingresa la ruta a la carpeta Iqtree y la subcarpeta del archivo ejecutable, que en este caso sería C:\...\Iqtree\bin
e. Se hace clic en la pestaña "Aceptar" en todas las ventanas externas para aplicar los cambios.

## Verificar la instalación:

Es importante verificar que la instalación fue la correcta, para lo cual en GitBash se escribe el comando "iqtree2 -h" para comprobrar que Iq-Tree se ha instalado con éxito en el PATH:

```
iqtree2 -h
```

# **Análisis Filogenético**

## Correr archivo alineado con Iq-Tree

a. Con el archivo fasta alineado usar el siguiente comando en Githbash:

```
iqtree2 -s musscle_galdi2.aln.fasta -B 1000
```

```
b. Se generaran varios archivos pero el que se debe escoger es el archivo "musscle_galdi2.aln.fasta.treefile" con la terminación treefile.

```
musscle_galdi2.aln.fasta.treefile
```

c. Visualizar el archivo con el programa FigTree.

Se visualiza el árbol al cual se le debe enraizar, se le puede mejorar tamaños de letras, color entre otras.
