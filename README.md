# Strings-D
## Métodos de Strings en Python
**1. Endswith:** se utiliza para comprobar si una cadena termina con una subcadena específica. Devuelve como resultado un booleano. Se puede utilizar para:verificar entradas de usuarios, procesar datos en función de sufijos específicos en cadenas o filtrar archivos por extensión.Ej:
```pseudocode
archivo = "documento.pdf"
if archivo.endswith(".pdf"):
    print("Es un archivo PDF")
```
**2. Startswith:** función de una cadena que verifica si una cadena comienza con un archivo específico.Al igual que la anterior, devuelve un resultado booleano. Ej:
```pseudocode
txt = "Bienvenido al curso de Python"

x = txt.startswith("Bien", 7, 20)

print(x) #Arroja como resultado False, pues, los índices no corresponden
```
Es importante recalcar que el 7 indica la posición de inicio desde donde se debe empezar a buscar el prefijo en la cadena; mientras que, el 20 indica la posición final desde donde se debe empezar a buscar el prefijo. Esto aplica tanto para _endswith_, como para _startswith_.
**3. Isalpha:** comprueba si una cadena está formada sólo por letras o no. Arroja un resultado booleano. Ej:
```pseudocode
print("abcdefgh".isalpha()) #arroja como resultado True
print("qwerty123456".isalpha()) #arroja como resultado False
```
**4. Isalnum:** comprueba si una cadena está formada sólo por carácteres alfanuméricos o no, es decir, si la cadena tiene letras del alfabeto o números. Arroja un resultado booleano. Ej:
```pseudocode
texto = "Python123"
resultado = texto.isalnum()
print(resultado)  # True, ya que todos los caracteres son alfanuméricos

texto = "Python 123"
resultado = texto.isalnum()
print(resultado)  # False, ya que hay un espacio en blanco que no es alfanumérico
```
**5. Isdigit:** verifica si en una cadena todos los elementos son números o dígitos. Ej:
```pseudocode
a = "\u0030" #unicode for 0 devuelve true
b = "\u00B2" #unicode for ² que devuelve false, porque este no es un dígito decimal válido
print(a.isdigit())
print(b.isdigit())
```
```pseudocode
txt = "40700"

x = txt.isdigit()

print(x)
```
**6. Isspace:** verifica si una cadena contiene sólo espacios en blanco. También arroja resultados booleanos. Ej:
```pseudocode
cadena = "   "
resultado = cadena.isspace()
print(resultado)  # True
```
**7. Istitle:** verifica si las palabras de una cadena tienen un formato de título, es decir, si las palabras empiezan con mayúscula y tienen minúsculas. Arroja el resultado True si la primera letra empieza con mayúscula y el resto son minúsculas,de lo contrario, arrojará False.
```pseudocode
cadena = "Hola Mundo"
resultado = cadena.istitle()
print(resultado)  # True
```
**8. Islower:** verifica si todos los carácteres en la cadena están en minúscula. Los carácteres especiales, símbolos o espacios no se toman en cuenta, sólo se evalúan los carácteres alfabéticos. Ej:
```pseudocode
a = "Hello world!"
b = "hello 123"
c = "mynameisPeter"

print(a.islower()) #False
print(b.islower()) #True
print(c.islower()) #False
```
**9. Isupper:** determina si todos los carácteres de la cadena están en mayúscula. Al igual que en el _islower_, no se toman en cuenta los carácteres especiales, símbolos o espacios, sólo se evalúan las letras. Ej:
```pseudocode
texto = "12345"
resultado = texto.isupper()
print(resultado)  # Resultado: False
```
**Referencias:** https://www.w3schools.com/python, https://thedataschools.com/python/strings, https://www.programiz.com/python-programming/methods/string.

## Procesar el archivo y extraer:
+ Cantidad de vocales.
+ Cantidad de consonantes.
+ Listado de las 50 palabras que más se repiten.

Lo primero que hice fue asignarle una variable a mi archivo para poder traerlo a Visual. Cabe aclarar que puse una r antes de la ubicación de mi archivo (la cual se encuentra en comillas sencillas), esto, porque cuando copié la dirección de mi archivo, los slashes estaban invertidos, entonces, para que no me interprete como barras de escape, estoy indicando que es una cadena cruda, es decir, una cadena que se toma como un valor literal.

Ahora, para abrir el archivo, utilicé el statement "with open()", el cual, al principio me pareció complicado para utilizar, sin embargo, después lo encontré muy útil cuando me explicaron todo en este <a href="https://elblogdelprogramador.com/posts/uso-correcto-del-statement-with-open-en-python-ejemplo-de-sintaxis/#gsc.tab=0">post</a>. Para este caso, sólo quería leer el archivo, por eso puse 'r' entre paréntesis y después de la variable que le asigné a mi archivo, así, todo lo que pusiera dentro de ese with se realizaría con mi archivo abierto.

También, usé el ciclo for para que me recorriera cada caracter del archivo y me determinara si es una vocal (sólo si hace parte de la lista que creé) o si es una consonante(si es un caracter alfanumérico y además no se encuentra en la lista). Finalmente, me basé en un post de Stackoverflow para poder contar las palabras que más se repiten.

![reto_12](https://github.com/Cate1911/Strings-D/assets/141857246/bf5b05ab-43eb-4050-8292-cd19719e9d58)

<a href="https://es.stackoverflow.com/questions/442488/qu%C3%A9-significa-la-letra-r-precediendo-una-constante-de-cadena">Referencia de lo de la cadena cruda:**</a>

<a href="https://es.stackoverflow.com/questions/444688/contar-caracteres-repetidos-en-una-cadena">El post que utilicé para guiarme en la última parte</a>

**¡Muchas gracias por haber leído mi repo! y ya, creo que es uno de los retos que más me ha gustado, tal vez por lo de procesar el archivo y usar strings**
