# Instalación y configuración de Hadoop en modo local (*standalone*)


Esta guía describe la instalación y configuración  de Apache Hadoop en modo standalone. 
Esta es la instalación más simple.


### Paso 1

Descargue Java SE Development Kit (JDE) 8u181 (jdk-8u181-windows-x64.tar.gz). 

http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html


### Paso 2

En el explorador de archivos, descomprima el archivo `jdk-8u181-windows-x64.tar.gz`. Encontrará el instalador de Java.


### Paso 3

Al ejecutar el instalador, cambie el directorio de instalación de Java por `C:\Java\jdk1.8.0_181\` para la primera disribución (JDK).

![alt](images/wdw-java-dir.PNG)

Luego, el instalador le pedirá una ruta para ubicar el archivo JRE. Cree un nuevo directorio desde el explorador de archivos dentro de `C:\Java` llamado `\jre1.8.0_181\` `(C:\Java\jre1.8.0_181\)` redireccione la segunda instalación hacia el.

![alt](images/wdw-java-dir2.PNG)


### Paso 4 

Descargue el archivo **binario** de Apache Hadoop 2.8.3 desde https://hadoop.apache.org/releases.html

![alt](images/apache-1.PNG)


### Paso 5

Descomprima el archivo desde el explorador de archivos, renombre el directorio como `hadoop` y ubiquelo en el disco `C:`.

    C:\hadoop\
    

### Paso 6

Descargue el siguiente repositorio y descomprimalo: https://github.com/steveloughran/winutils

Del directorio `hadoop-2.8.3\bin` copie pegue todos los archivos de  `bin` y peguelos en el directorio `C:\hadoop\bin` reemplazando los contenidos originales.

### Paso 7

Abra en el panel de control la opción  `Editar las variables de entorno del sistema` y realice los siguientes cambios:

> Agregue las siguientes variables

    HADOOP_HOME = C:\hadoop
    JAVA_HOME = C:\Java\jdk1.8.0_181
    HADOOP_CLASSPATH = %JAVA_HOME%\lib\tools.jar
    
![alt](images/var-1.png)

![alt](images/var-2.PNG)
    
> Modifique la variable PATH. Agregue:

    C:\Java\jdk1.8.0_181\bin
    C:\hadoop\bin

![alt](images/var-3.PNG)


### Paso 8

Digite `hadoop fs -dir` en la línea de comandos. 
Como resultado, debe imprimirse que el comando `-dir` no existe y adicionalmente la ayuda de hadoop en la pantalla.


**Nota.--** En este paso, Apache Hadoop se puede ejecutar en modo *standalone*.

**Nota.--** Hadoop usará el sistema local de archivos como sistema HDFS.
