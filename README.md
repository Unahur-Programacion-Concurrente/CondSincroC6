# Ejercicios con Locks

## Cola FIFO concurrente

El siguiente archivo python contiene la definición de la clase *ColaFIFOconcurrente* que implementa una cola First In, First Out segura para hilos y cuyos métodos para extraer e insertar esperan dormidos si encuentran la cola vacía o llena.

## Ejercicio

1. Leer y analizar que hace el código de este programa. 
**Analizar hasta comprender todas las líneas del código**

2. En un archivo python separado, importar la clase ColaFIFOconcurrente, instanciar una cola de ésta clase, **de tamaño infinito** y luego implementar un programa que ejecute las siguientes threads:

	 - Una thread (productor) que ejecute un loop infinito que en cada iteración inserte en la cola un valor numérico generado aleatoriamente (con valores entre 0 y 100), imprima un mensaje de logging indicando que se realizó la inserción y espere (sleep) una tiempo aleatorio entre 1 y 5 segundos.
	
	  **Esta thread debe recibir como argumentos un objeto ColaFIFOconcurrente y un valor numérico (retardo en segundos).**
		  Por ejemplo:
      ````
        # a partir de una clase derivada de Thread
        c1 = Cons(cola, random.randint(1,5)) 
      
        # directamente desde el módulo threading 
        c1 = threading.Thread(target=cons, args=(cola, random.randint(1,5))
      ````
  
   - Una thread (consumidor) que ejecute un loop infinito que en cada iteración extraiga un elemento de la cola, genere un mensaje de logging con el valor del elemento extraído y luego espere (sleep) un tiempo aleatorio entre 1 y 5 segundos.  

	  **Esta thread debe recibir como argumentos un objeto ColaFIFOconcurrente y un valor numérico (retardo en segundos).**
    
    Ejemplos: 
    ```
      # a partir de una clase derivada de Thread
      p1 = Prod(cola, random.randint(1,5) 
     
      # directamente desde el módulo threading 
      p1 = threading.Thread(target=prod, args=(cola, random.randing(1,5))  
    ```

    **Preferentemente, implementar estas threads a partir de clases derivadas de Thread que reciban como argumento el objeto de clase ColaFIFO instanciado y el valor numérico de retardo, en vez de hacerlo directamente del módulo threading.**

    **Las threads deben permanecer ejecutándose indefinidamente, no debe terminar el programa después de lanzarlas. Coloque todo el código que sea necesario para esto.**

3. Modifique el programa de modo de instanciar una nueva cola de tamaño (size) 10 y que lance 6 hilos productores y 6 consumidores iguales a los del ejercicio anterior.
