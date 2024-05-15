Nombre Rita Maria Patricia Sipaque Zil   FECHA: 15/05/2024
PLAN DE ATAQUE 

1.Generacion de Numero Aleatorio Inadecuada:
El numero aleatorio solo se genera entre 0 y 10, deberia ser de 1 a 100 como se nos indica en el requerimiento
Error: La generacion del numero aleatorio no esta dentro del rango correcto. Actualmente, esta generando un numero entre 0 y 10
codigo : let randomNumber = Math.random() * 10; 

Solucion: 
codigo: let randomNumber = Math.floor(Math.random() * 100) + 1;
Math.random() * 100 nos dara numeros entre 0 y 99
Al aplicar Math.floor() redondeamos a entero el numero obtenido.
Y sumandole 1 al resultado, quedara entre 1 y 100 como se requiere.

2.La comparacion entre el numero ingresado por el usuario y el numero aleatorio no esta considerando el tipo de dato (numeros vs. cadena de texto).
ERROR:La comparacion entre el numero ingresado por el usuario y el numero aleatorio no esta considerando el tipo de dato lo cual no esta permitiendo que actualmente la comparacion se realiza entre un numero y una cadena de texto, lo que puede causar resultados inesperados o errores en la logica del juego.

codigo : let userGuess = guessField.value;

Solucion: Convertir la entrada del usuario a un numero entero antes de compararlo con el numero aleatorio , esto permitira que ambas variables sean del mismo tipo de dato y que la comparacion se realice correctamente. Se puede lograr utilizando la funcion parseInt() para convertir la cadena de texto ingresada por el usuario a un numero entero.

codigo: let userGuess = parseInt(guessField.value);

3. Errores de Sintaxis
Hay un error de escritura en el metodo addEventListener cuando se agrega el manejador de eventos al elemento guessSubmit.
ERROR: guessSubmit.addeventListener('click', checkGuess) y resetButton.addeventListener('click', resetGame);;

Solucion :Corregir el error tipografico cambiando addeventListener a addEventListener
codigo: guessSubmit.addEventListener('click', checkGuess); y resetButton.addEventListener('click', resetGame);

4.Logica de Juego Equivocada
Las condiciones para determinar si el jugador ganaba o perdia estaban invertidas.
Impacto: Confusion en las reglas del juego donde el mensaje de ganar o perder no se correspondia con la realidad del juego.

Solucion: Asegurarse de que las condiciones de victoria y derrota esten correctamente implementadas.
Codigo: Implementacion correcta de condiciones if/else en la funcion checkGuess.

5.Seleccion Incorrecta de Elementos DOM
Error: Seleccion incorrecta y falta de seleccion adecuada para algunos elementos
codigo:document.querySelector('lowOrHi')

Solucion: Asegurar que todas las selecciones de elementos del DOM sean correctas y coherentes.
Codigo: Uso de document.querySelector('.lowOrHi') para la seleccion correcta.

6.Ajuste en el Numero de Intentos
Error: El numero de intentos estaba incorrectamente establecido en el codigo original, lo que limitaba al jugador a solo 5 intentos en lugar de los 10 intentos requeridos.
codigo:ATTEMPS = 5

Solucion: Se corrigio el numero de intentos aumentandolo a 10 para cumplir con los requisitos del juego
codigo: ATTEMPTS = 10

7.Entrada invalida del usuario al intentar adivinar el numero
Error: El codigo original no incluia una validacion para asegurar que el usuario ingresara un numero valido al intentar adivinar, lo que podria causar errores si se ingresaba texto u otros caracteres no numericos.

solucion 
Se implemento una validacion utilizando la funcion isNaN() para verificar si el valor ingresado por el usuario es un numero valido. En caso de que el valor no sea valido, se muestra una alerta solicitando al usuario que ingrese un numero valido y se detiene la ejecucion de la funcion para evitar posibles errores.

codigo:
function checkGuess() {
    let userGuess = parseInt(guessField.value);
    if (isNaN(userGuess)) {
        alert("Por favor ingresa un número válido.");
        return;
    }
