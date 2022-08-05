# I7
Como usar la biblioteca estatica
1.- Comandos utilizados para compilar bibliotecas dinámicas y estáticas.
▪ Para compilar bibliotecas estáticas se deben utilizar los comandos:
g++ -c . Ruta del archivo .cc -o Ruta del archivo.o -I ruta de la biblioteca
Por ejemplo: g++ -c .\src\calor.cc -o .\obj\hooke.o -I .\include
Donde -c obtiene el código maquina del archivo .c, -o se emplea para el Código salida y -I Indica el directorio de la cabecera necesaria para compilar.
Después se crea la biblioteca con el comando ar crs que creara el archivo compacto de los archivos .o en un archivo con extensión .lib
▪ Para compilar una biblioteca dimanica se deben utilizar los siguientes comandos:
g++ -c . Ruta del archivo .c -o Ruta del archivo.o -fPIC
Por ejemplo: g++ -c .\src\calor.cc -o .\obj\subtraction.o -fPIC
Donde el fPIC indica al compilador que las direcciones no van a depender del código que invoque.
Posteriormente se utiliza el comado g++- share que genera un archivo comprimido con extensión .dll. Para compilarlo es necesario indicar que existe una biblioteca y donde se encuentra por ejemplo: g++ .\main.cc -o test -L . -l Fisica donde -L indica la ruta de la biblioteca con las funciones y -l indica el nombre de dicha biblioteca
2) Como compilar una aplicación que:
a) Emplea bibliotecas estáticas
Es necesario primero compilar el código fuente con el comando g++ -c, después de debe crear la biblioteca mediante el comando ar que compactara los archivos .o en un archivo.lib, posteriormente el necesario compilar todo el ejecutable con el comando g++ main.cc -o Nombre del ejecutable -I Ruta relativa -L Ruta de la biblioteca -lnombre de la biblioteca y posteriormente se podrá utilizar el ejecutable
b) Emplea bibliotecas dinámicas
Primero es necesario compilar el código fuente de forma similar a la siguiente:g++ -c .\src\calor.cc -o .\obj\calor.o -fPIC.
Después se debe hacer el archivo compartido con extensión .dll y compilar el programa indicando donde se encienta la biblioteca y el nombre de la misma.
Si se hacen correctamente los pasos se podrá utilizar el ejecutable sin problema.
