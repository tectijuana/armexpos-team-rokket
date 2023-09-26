![](https://s3.amazonaws.com/videos.pentesteracademy.com/videos/badges/low/arm-assembly.png)

Borrar y modificar a su gusto este README, pero antes utilizar estas condiciones de entrega del trabajo.

# Utilizar los dos directorios

- code  - ahi depositar sus programas los ***archivos extensión *.s****  (Source File) algunos autores en x86 de ponen .asm y en otras plataformas ARM compatibles la extension *.elf
- Todo programa lleva su comentario en la parte de arriba, objetivo y nombre del programador minimo.
- images  - de haber algo de pantallas ahi se presentaran, su busca documentarlas en MARKDOWN el código es:

``` ![](images/---archivo.jpg---) recordar que no lleva espacios```



- Programa en MarkDown es inicia con tres tildes * (`) sin espacio, seguido de el lenguaje de programacion, al final del codigo se poner otra vez los mismos tilder..

No se usan espacios en nombres de archivos, usar los nombres estilo camelCase (primera palabra minusculas, mayuscula solo la 1ra letra de cada palabra subsecuente):  ejemplo: sensorHumo, etc.

Suerte.

Att. ![](https://img.icons8.com/color/2x/docker.png)

------

<pre>

	<p align=center>

Tecnológico Nacional de México
Instituto Tecnológico de Tijuana
		
Departamento de Sistemas y Computación
Ingeniería en Sistemas Computacionales

Semestre:
Junio - Diciembre 2023

Materia:
Lenguajes de interfaz

Docente:
M.C. Rene Solis Reyes 

Unidad:
1

Título del trabajo:
Exposición Instrucciones ARM32 

Estudiante:
Galvan Godinez Antonio de Jesus 20211777
Gallardo Dueñas Eduardo 21212215 
Gutierrez Martinez Ana Cristina 21211959
Ortiz Garcia Nayeli 21210406
Rodriguez Cruz Luis Fernando 21210421 
Rojo Chaidez Donovan 21210424	
	</p>

</pre>

<pre>

	<p align=left>
Instrucción Load (Cargar): 
Propósito: La instrucción Load se utiliza para cargar datos desde la memoria principal (RAM) 
en un registro de la CPU. Puede ser un registro general, como un registro de propósito general o un registro específico 
para datos, como un registro de carga (load register). 
Funcionamiento: La instrucción Load especifica la dirección de memoria desde la cual se deben 
cargar los datos y el registro de destino en la CPU donde se almacenarán los datos cargados. 
Los datos se transfieren desde la memoria a la CPU a través del bus de datos. Uso común: Las instrucciones 
Load son esenciales para cargar variables, valores, y datos de entrada desde la memoria 
a la CPU, lo que permite a la CPU realizar cálculos y operaciones con esos datos.
Ejemplo: Imaginemos que tenemos una variable llamada "valor" almacenada en una 
dirección de memoria específica. 
En lenguaje ensamblador, podemos cargar su valor en un registro de la CPU de la siguiente manera:

|LOAD R1, valor   ; Carga el valor de la dirección de memoria 'valor' en el registro R1|


Instrucción Store (Almacenar): 
Propósito: La instrucción Store se utiliza para almacenar datos desde un registro 
de la CPU en una ubicación específica de la memoria principal (RAM).
Funcionamiento: La instrucción Store especifica la dirección de memoria de destino donde se 
almacenarán los datos desde el registro de la CPU. Los datos se transfieren desde el registro a 
la memoria a través del bus de datos. Uso común: Las instrucciones Store son fundamentales para 
guardar resultados de cálculos, variables modificadas y datos de salida en la memoria, de modo que 
puedan ser accedidos posteriormente o utilizados por otros componentes del sistema.
Ejemplo: Supongamos que, después de realizar un cálculo en la CPU, deseamos almacenar el resultado en 
una ubicación de memoria particular. La instrucción Store se usa de la siguiente manera:

STORE R2, resultado; Almacena el contenido del registro R2 en la dirección de memoria 'resultado'


Load and Store Multiple

"Load and Store Multiple" es un tipo de instrucción comúnmente encontrada en arquitecturas de 
computadoras, incluyendo ARM, que permite cargar o almacenar múltiples registros en la 
memoria en una sola instrucción. 
En el contexto del lenguaje ensamblador de ARM, esto se logra típicamente mediante las instrucciones 
LDM (Load Multiple, Cargar Múltiples) y STM (Store Multiple, Almacenar Múltiples). 
Estas instrucciones se utilizan para transferir datos eficientemente entre los 
registros de la CPU y la memoria.

Carga Múltiple (LDM): La instrucción LDM se utiliza para cargar múltiples registros 
con datos desde ubicaciones de memoria consecutivas. 
Permite cargar un conjunto de registros desde la memoria de manera eficiente. Los registros suelen 
especificarse como una lista, y también se proporciona la dirección base en memoria desde la 
cual se cargan los datos.
Por ejemplo, en el ensamblador de ARM, podríamos ver algo como esto:
		
LDMIA R0, {R1, R2, R3, R4}
		
Esta instrucción carga los valores de la memoria en la dirección apuntada por el registro R0 en los 
registros R1, R2, R3 y R4.
La terminación "IA" en LDMIA significa "Increment After" en el contexto de ARM assembly. 
Increment After (IA): En este modo, después de que se completa la operación de carga múltiple, 
el valor del registro base (R0) se incrementa en la cantidad total de bytes transferidos. 
En otras palabras, R0 se actualizará para apuntar a la siguiente ubicación de memoria después 
de los datos que se acaban de cargar. Esto quiere decir que después de cargar ‘R0’ se 
carga ‘R1’, ‘R2’ y así sucesivamente.
		
Almacenamiento Múltiple (STM): La instrucción STM se utiliza para almacenar los valores 
de múltiples registros en ubicaciones de memoria consecutivas. 
Permite almacenar un conjunto de registros en la memoria de manera eficiente. 
Al igual que con LDM, se especifican los registros a almacenar y la dirección base 
en la memoria donde deben almacenarse los datos.

		STMIA R0, {R1, R2, R3, R4}
		
Las instrucciones de Carga y Almacenamiento Múltiples son útiles para tareas que 
implican mover bloques de datos en memoria de manera eficiente, como copiar
arreglos o trabajar con estructuras de datos. Pueden ayudar a reducir la cantidad de instrucciones 
individuales de acceso a memoria, lo que puede mejorar la eficiencia y el rendimiento del programa.

Arm Instructions
Características principales del Conjunto de Instrucciones ARM
Todas las instrucciones son de 32 bits.
La mayoría de las instrucciones se ejecutan en un ciclo.
Cada instrucción se puede ejecutar condicionalmente.
Una arquitectura load/store 
Instrucciones de procesamiento de datos actúan solo en registros
Formato de tres operandos
ALU y shifter combinados para una manipulación rápida de bits
Instrucciones de acceso a memoria específicas con potentes modos
indexados de direccionamiento
32 bit y 8 bit tipos de datos
Y también 16 bit tipos de datos en ARM 4.
Instrucciones de registro multiple flexible load and store 
Conjunto de extensión de instrucciones via coprocesadores

Modos del Procesador
ARM tiene seis modos de operación:  
User (unprivileged mode under which most tasks run)  
FIQ (entered when a high priority (fast) interrupt is raised) 
IRQ (entered when a low priority (normal) interrupt is raised)  
Supervisor (entered on reset and when a Software Interrupt instruction is executed)  
Abort (used to handle memory access violations)  
Undef (used to handle undefined instructions)  
Arquitectura ARM Versión 4 agrega un séptimo modo:  
System (privileged mode using the same registers as user mode

Thumb Instructions
Las "Thumb Instructions" (instrucciones Thumb) se refieren a un conjunto de 
instrucciones de código de máquina utilizadas en arquitectura ARM de 32 bits,
específicamente en la modalidad Thumb. 
La arquitectura ARM, desarrollada por ARM Holdings, es ampliamente utilizada en
una variedad de dispositivos, incluyendo teléfonos móviles, tabletas, dispositivos 
integrados y sistemas embebidos.
La modalidad Thumb fue diseñada para mejorar la eficiencia del código y reducir 
el tamaño de los programas en sistemas con limitaciones de memoria y ancho de banda, 
como dispositivos móviles y sistemas embebidos. En lugar de utilizar las 
instrucciones ARM de 32 bits completas, las instrucciones Thumb son de 16 bits de longitud y 
proporcionan un conjunto reducido de operaciones.

1- Longitud reducida: Las instrucciones Thumb son de 16 bits, lo que significa que ocupan
la mitad de espacio en memoria en comparación con las instrucciones ARM de 32 bits.
2- Conjunto de instrucciones reducido: Thumb ofrece un subconjunto de instrucciones 
ARM completo, lo que significa que no todas las instrucciones ARM están disponibles en Thumb. 
Sin embargo, Thumb incluye las instrucciones más comunes y es adecuado 
para la mayoría de las aplicaciones.
3- Menor consumo de energía: La ejecución de instrucciones Thumb puede consumir menos 
energía que las instrucciones ARM completas, lo que es beneficioso para dispositivos 
con restricciones de energía, como dispositivos móviles.
4- Mejora del rendimiento en caché: Debido a su tamaño reducido, las instrucciones 
Thumb pueden almacenarse de manera más eficiente en la memoria caché, lo que puede 
llevar a un mejor rendimiento en ciertos escenarios.

	</p>

</pre>
