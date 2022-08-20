# I7
##  Compilación de bibliotecas dinámica y estática
### Biblioteca estática
Para compilar bibliotecas estáticas se deben utilizar los comandos:  
**g++ -c . Ruta del archivo .cc -o Ruta del archivo.o -I ruta de la biblioteca**  
Por ejemplo: g++ -c .\src\calor.cc -o .\obj\hooke.o -I .\include  
Donde -c obtiene el código maquina del archivo .c, -o se emplea para el Código salida y -I Indica el directorio de la cabecera necesaria para compilar.  
Después se crea la biblioteca con el comando:  
**ar crs .\lib\static\fisica.lib .\obj\*.o**  
ar crs que creará el archivo compacto de los archivos .o en un archivo con extensión .lib  

### Biblioteca dinámica
Para compilar una biblioteca dimanica se deben utilizar los siguientes comandos:  
**g++ -c . Ruta del archivo .c -o Ruta del archivo.o -fPIC**  
Por ejemplo: g++ -c .\src\calor.cc -o .\obj\subtraction.o -fPIC  
Donde el fPIC indica al compilador que las direcciones no van a depender del código que invoque.  
Posteriormente se utiliza el comado:  
**g++ -shared .\lib\obj\*.o -o fisica.dll**  
g++- share que genera un archivo comprimido con extensión .dll.   
Para compilarla es necesario indicar que existe una biblioteca y donde se encuentra en este caso el comando es:  
**g++ .\main.cc -o test -L . -l Fisica**   
donde -L indica la ruta de la biblioteca con las funciones y -l indica el nombre de dicha biblioteca  



## Compilacion de aplicaciones que emplean:
### Bibliotecas estáticas
1. Es necesario primero compilar el código fuente con el comando g++ -c  
2. Después de debe crear la biblioteca mediante el comando ar que compactara los archivos .o en un archivo.lib
3. Posteriormente el necesario compilar todo el ejecutable con el comando g++ main.cc -o Nombre del ejecutable -I Ruta relativa -L Ruta de la biblioteca -lnombre de la biblioteca 
4. Listo la biblioteca podrá ser utilizada el ejecutable

### Bibliotecas dinámicas
1. Es necesario compilar el código fuente de forma similar a la siguiente: g++ -c .\src\calor.cc -o .\obj\calor.o -fPIC.
2. Se debe hacer el archivo compartido con extensión .dll y compilar el programa indicando donde se encienta la biblioteca y el nombre de la misma.
3. Si se hacen correctamente los pasos se podrá utilizar el ejecutable sin problema.



## Estructura de directorios 
**Este fue el directorio utilizado para la creación de las bibliotecas. No es la estructura del directorio del repositorio**

C:.

│   main.cc  
│  
├───app  
│       testdll.exe  
│       teststatic.exe  
│       test_AceleracionRendimiento.cc  
│       test_CalorLongitudOnda.cc  
│       test_NewtonHookeTorque.cc  
│  
├───include  
│       Fisica  
│  
├───lib  
│   ├───dynamic  
│   │       Fisica.dll  
│   │  
│   └───static  
│           Fisica.lib  
├───obj  
│       aceleracion.o  
│       Calor.o  
│       hooke.o  
│       LongitudOnda.o  
│       newtontwo.o  
│       rendimiento.o  
│       torque.o  

└───src  
│       aceleracion.cc  
│       Calor.cc  
│       hooke.cc  
│       LongitudOnda.cc  
│       newtontwo.cc  
│       rendimiento.cc  
│       torque.cc  
        
        
        
## Sección de ejemplos
En esta seccion se ilustran como utilizar cada funcion implementada en la biblioteca 
La biblioteca compilada ofrece difertentes formulas de magnitudes físicas. 
Para utilizar estas fórmulas es necesario poner el nombre de la función y los argumentos de la siguiente forma para obtener los siguentes resultados: 
1. Aceleración
  - *aceleracion (double velocidad inicial, double velocidad final, double tiempo)*
  -  return (vf-vi)/t 
2. Calor
  -*calor (double incremento de calor, double incremento de temperatura)*
  - return Q/T
3. Ley de Hook
  - *hooke (double contante de resorte, double longitud de resorte)*
  - return k * l
4. Longitud de onda 
  - *longitud ( double velocidad de la onda, double frecuencia)*
  - return v/f
5. Seguna ley de Newton
  - *newtontwo (double aceleracion, double masa)*
  - return m * a
7. Rendimiento
  - *rendimiento (double energia toatl, double enregia util)* 
  - return eu/eT
9. Torque
  - *torque (double vector fuerza, double vector distancia)
  - return m * f
  

