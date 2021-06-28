# Implementación paralela de sumatoria trigonométrica

El objetivo de la tarea es diseñar e implementar una versión paralela de una sumatoria de funciones trigonométricas, utlizando MPI con C++17 a través de boost::MPI. Deberá realizar experimentos que permitan mostrar el desempeño temporal del algoritmo implementado, utilizando métricas de SpeedUp e Eficiencia. Los resultados de los experimentos serán mostrados a través de gráficos con su correspondiente explicación y análisis.

# Descripción del trabajo a realizar

## Antecendentes

En el código inicial que usted utilizar, se entrega la implementación secuencial de la siguiente expresión:

```
    N
   ,---.
   \ 
S = |   sin(x)·cos(x) , donde x~U[0,10000]
   /
   `---´
   i=0
```

La suma secuencial es realizada por en proceso 0. El tiempo de procesamiento se almacena en la variable ```tiempoSecuencial```  y el resultado (```sumaSecuencial```) es utilizado en forma posterior para comprobar que la suma paralela sea idéntica a la secuencial.

## Diseño del algoritmo paralelo

A partir del código entregado, deberá realizar el diseño del algoritmo paralelo que usted finalmente implementará. Deberá incluir diagramas de alto nivel para explicar el funcionamiento y diagramas temporales para explicar la dinámica del algoritmo implementado. Todo diagrama debe estar explicado. Además, deberá explicar las pruebas que realizó para asegurar que su implementación efectivamente realiza en forma correcta la suma paralela.

## Experimentos

Una vez implementado el algoritmo paralelo, deberá realizar pruebas de desempeño de él. Para esto, fijará la cantidad de números aleatorios a sumar (variable N en la sumatoria mostrada) a N=50000000 (50 millones), y variará la cantidad de procesos utilizados en el rango P={1,2,..,16}. Por cada valor de P, deberá obtener el speedUp e eficiencia. Estos resultados deberá graficarlos y explicarlos en su informe.


# Entregables

### Código
El código de su trabajo deberá ser copiado en el directorio ```/projects/$USER/tarea04``` para su revisión. La estructura de este directorio debe ser:

```
/projects/$USER/
	+ tarea04/
		+ code/
			- Makefile
			- run.sh
			+ src/
		- README.txt	
```

El archivo README.txt deberá contener una descripción de los directorios y de su contenido. El directorio ```src``` debe tener la misma estructura de las tareas anteriores. Recuerde que su código debe ser compilado con el comando ```make```. La secuencia para ejecutar su código es:

```
$ cd /projects/$USER/tarea04/code
$ make
$ ./run <P> <N> 
Salida de los experimentos realizados...
```
, donde ```<P>```: cantidad de procesos a utilizar, ```<N>```: cantidad de de número aleatorios a sumar.
El script ```run.sh``` es un cargador que tiene las llamadas correctar a MPI para ejecutar su programa.

### Informe escrito

Usted debe preparar un informe del trabajo realizado, utilizando la plantilla entregada ```plantilla-informe.dotx```. El informe deberá subirlo al Aula Virtual, y el nombre del archivo debera ser: ```Apellido1-Apellido2-Nombre.pdf```.
