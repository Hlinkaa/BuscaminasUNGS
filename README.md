# BuscaminasUNGS
Organización del Computador

Trabajo Práctico – ARM
2025

# Propósito y sentido de la actividad

En este trabajo se desarrollarán e integrarán los conceptos de arquitectura ARM
abordados durante la segunda parte de la materia, posterior al primer parcial. El
foco estará puesto especialmente en los siguientes temas:

  - Manejo de datos en registros, pila y memoria
  - Modos de direccionamiento
  - Llamadas a procedimientos definidos por el usuario e interrupciones del
  sistema

El proyecto se plantea en el contexto de un videojuego ejecutado desde la consola o
terminal. Este entorno, además, permitirá retomar y aplicar conceptos ya vistos en la
primera parte del curso, tales como:

  - Codificación de caracteres ASCII
  - Conversión entre sistemas numéricos (Decimal ↔ Binario)
  - Operaciones en complemento a dos (A2)
  
# Producto final de la actividad

Al finalizar este trabajo, se obtendrá un programa funcional desarrollado
íntegramente en lenguaje ensamblador ARM, capaz de ejecutarse en consola.
Además, se habrán generado una serie de subrutinas reutilizables para futuros
desarrollos en este entorno.

# Evaluación

- El nombre del archivo entregado debe seguir el formato:
TP_Final_Orga_NumeroDeGrupo.pdf
- Fecha límite de entrega: (consultar en Moodle)
- Modo y espacio de entrega: (consultar en Moodle)

# Enunciado del TP

# El Juego del BUSCAMINAS

El juego del Buscaminas consiste en una cuadrícula de casillas que ocultan minas
distribuidas aleatoriamente. El objetivo del jugador es destapar todas las casillas
que no contienen minas, utilizando como guía la cantidad de minas adyacentes
reveladas en cada jugada. Si se selecciona una casilla con una mina, el jugador
pierde la partida.

# Implementación en ARM

Debido a las limitaciones gráficas del sistema, el mapa será representado utilizando
caracteres ASCII, y la selección de casillas se realizará ingresando por teclado la
fila y columna correspondientes.

A diferencia del juego original, en esta versión solo se contará como "vecinas" las
casillas directamente adyacentes en dirección vertical y horizontal (no se
considerarán las diagonales). Si la casilla elegida no contiene una mina, se mostrará
la cantidad de minas adyacentes según esta lógica.

Al inicio del juego, el usuario deberá seleccionar un nivel de dificultad y el tamaño,
los tamaños posibles del mapa son de 8x8 u 12x12), la cantidad de minas
distribuidas en él, para el nivel inicial, 20% de las casillas son minas, para el
intermedio 30% y para el difícil 50%. Las minas deberán ser generadas
aleatoriamente para cada partida y no deberían estar contiguas, es decir no pueden
estar todas las filas verticales pegadas, ni todas las horizontales, debe haber
espacios entre minas. Para los porcentajes redondear hacia abajo.

El jugador selecciona una casilla indicando fila y columna, si la casilla no contiene
minas, se marcara con un carácter y se descubrirán todas las minas adyacentes con
otro carácter. En el nivel inicial deberá detectar 10 lugares sin minas para ganar. En
el intermedio 20 y en el difícil 25

Si el jugador selecciona una casilla con una mina, el juego finalizará mostrando las
casillas con minas y notificando la derrota. En caso de ganar (es decir, descubrir
todas las casillas sin minas solicitadas), se deberá registrar el nombre del jugador
y el tiempo total de juego y nivel en un archivo externo .txt.

Al finalizar cada partida ganada, el programa mostrará por consola los últimos tres
jugadores ganadores, junto con su tiempo.
Debe haber mensajes al usuario indicando si comenzó el juego.
Si debe ingresar la fila y columna
Cuantas minas le falta descubrir.
Si perdió o si gano.
Toda mejora en la interfaz presentada será considerada.
Esquema general y pseudocódigo

Es obligatorio escribir la lógica general del programa en forma de pseudocódigo
antes de su implementación. Este pseudocódigo deberá ser discutido con el docente
durante la instancia de control de avance, según el calendario de la comisión.

# Subrutinas mínimas requeridas:
*
- leer_ranking abre el archivo .txt
- escribir_ranking escribe dentro del archivo de ranking
- pedir_nombre solicita y guarda el nombre del usuario
- pedir_columna_y_fila solicita la posicion de la celda
- buscar_elemento_en_posicion Obtiene el elemento en la posicion
- calcular_tiempo_de_juego calcula el tiempo del juego
- verificar_mina verifica si la celda elegida tiene una
  mina  
- calcular_minas_cercanas calcula la cantidad de minas aledañas
- mostrar_mapa muestra por pantalla el mapa
- mostrar_minas escribe en el mapa el resultado de la
  celda elegida
- generar_random genera número randoms
- verificar_celda_repetida verifica que la celda elegida ya no haya
  sido seleccionada anteriormente
- pasar_numero_a_ascii pasa un número a caracter ascii
- pasar_ascii_a_numero pasa un caracter ascii a numero

# Funcionalidades extra (opcionales)

● Uso de colores en la terminal para mejorar la visualización
● Posibilidad de personalizar la cantidad de minas
● Elección de otro tamaño de tablero.

# Comentarios generales

Es fundamental consultar el pseudocódigo con su docente antes de comenzar con
la implementación en ensamblador. Recomendamos revisar el calendario
académico para conocer la fecha exacta del control de avance.
Imagenes orientativas
