//El programa ha sido diseñado para permitir que un microcontrolador STM32 reciba señales seriales provenientes de una pantalla Nextion
//a través de los puertos UART. Mediante el análisis de las señales UART recibidas, el programa se encarga de activar selectivamente
//ciertos pines de salida en función de la señal UART detectada.*/

// Agregamos las librerias necesarias
//#include "string.h"
// revisar que este libreria este incluida para evitar problemas con el "strlen"

// Definimos las funciones de prueba 
//void TestDet(void);
//void TestHscbwod(void);
//void TestHscdsind(void);

// Variables para las secuencias de caracteres*/
// Tiene como objetivo enviar diferentes secuencias de caracteres a través de una conexión serial.
// Las secuencias predefinidas son "INICIO\r\n", "TEST\r\n" y "FIN\r\n".
// Estas secuencias pueden ser utilizadas para probar la comunicación serial y verificar la recepción correcta de los datos.

// Antes de ejecutar el programa, asegúrate de tener configurada correctamente la comunicación serial y los puertos correspondientes.

	
// "byte" Esta variable es la que va almacenar un valor de 8 bits sin signo que recibe el UART 2 

// El ciclo " while (1)" siempre se va estar ejecutando, en este vamos a llamar a la biblioteca HAL.
// "Receive_IT" nos indica que la recepción se realiza de forma asíncrona mediante interrupciones.

//  Indicamos que vamos a estar recibiendo la señal por el "&huart2".
//  "&byte" va ha representar el puntero a la variable donde se almacenará el byte recibido.
//  "1" especifica la cantidad de bytes que desamos recibir.  
//  La función "switch" permite ejecutar diferentes bloques de código dependiendo del valor de una expresión,
//  proporcionando una estructura más clara y legible en comparación con el uso de múltiples sentencias if-else anidadas.
 
//  Para este codigo se crean 4 diferentes casos los cuales se van ir ejecutando dependiendo de la opcion que detecte el switch
//  "case 'a'" Utiliza la función HAL_UART_Transmit de la biblioteca HAL para enviar los datos especificados.
//  "&huart4" Representa la configuración y estado del periférico UART4.
//  (uint8_t*)"TestDet" Es un puntero al búfer que contiene los datos a transmitir. En este caso, se está enviando la cadena
//  de caracteres "TestDet".
//  strlen("TestDet") Es la longitud de los datos a transmitir. La función strlen se utiliza para determinar la longitud
//  de la cadena de caracteres.
//  1000 Es el tiempo máximo de espera en milisegundos para que se complete la transmisión. Si la transmisión no se completa
//  dentro de este tiempo, la función retornará un estado de error.
//  TestDet() Esta línea de código llama a una función llamada TestDet().
 
//  case 'b' transmite una señal serial atravez del HUART 4, que en este caso es una cadena de caracteres "TestHscbwod",
//  se define la longitud de caracteres con la funcion strlen y por ultimo definimos el tiempo maximo de espera
//  que en este caso es 1000 milisegundos, si la transmisión no se completa
//  dentro de este tiempo, la función retornará un estado de error.
//  Se introduce un retraso de 10 milisegundos en la ejecución del programa.
//  TestHscbwod() Esta línea de código llama a una función llamada TestHscbwod().

//  case 'c' transmite una señal serial atravez del HUART 4, que en este caso es una cadena de caracteres "TestHscdsind",
//  se define la longitud de caracteres con la funcion strlen y por ultimo definimos el tiempo maximo de espera
//  que en este caso es 1000 milisegundos, si la transmisión no se completa
//  dentro de este tiempo, la función retornará un estado de error.
//  Se introduce un retraso de 10 milisegundos en la ejecución del programa.
//  TestHscbwod() Esta línea de código llama a una función llamada TestHscbwod().

//  case 'd' transmite atravez del puerto HUART 3, la variable de caracteres definida arriba como Test, Test1, Test2.
//   lo cual tranmite mensajes como "INICIO" con un posterior delay de 2 segundos, "TEST" con un posterior delay de 10 segundos  y "FIN".
   
// Este código se ejecuta cuando la variable evaluada en un switch es igual a 'd'. A continuación, se transmiten datos a través de una comunicación UART 
// utilizando tres buffers diferentes: Test, Test1 y Test2. Después de cada transmisión, se introduce un retraso de tiempo antes de pasar a la siguiente transmisión. 
// Los retrasos pueden tener el propósito de esperar a que el receptor procese los datos antes de enviar más información.
// TestDet: Esta función realiza una secuencia de operaciones y transmisiones a través de la comunicación UART. Primero, se envía la cadena "TestDet1" a través de la 
// UART. Luego, se cambian los estados de varios pines GPIO, estableciéndolos en valores específicos. Después, se entra en un bucle while que se ejecutará hasta que se 
// cumpla una de las dos condiciones: el valor de timeout sea mayor o igual a 10 o el valor de aux sea igual a 1. Dentro del bucle, se introduce un retraso de
// 1 segundo, se incrementa el valor de timeout y se lee el estado de un pin GPIO específico.
// Al finalizar el bucle, se envía la cadena "FinFnctn1" a través de la UART.

// TestHscbwod: Esta función es similar a TestDet, pero realiza una secuencia de operaciones y transmisiones ligeramente diferentes. Primero, se envía la cadena 
// "TestHscbwod2" a través de la UART. Luego, se cambian los estados de varios pines GPIO. A continuación, se ejecuta un bucle while similar al de TestDet. 
// Finalmente, se envía la cadena "FinFnctn2" a través de la UART.

// TestHscdsind: Esta función también sigue un patrón similar a las anteriores. Primero, se envía la cadena "TestHscdsind3" a través de la UART.
// Luego, se cambian los estados de varios pines GPIO. Después, se ejecuta un bucle while similar a los otros dos casos. Al finalizar el bucle, 
// se envía la cadena "FinFnctn3" a través de la UART.# banco-HSCB
