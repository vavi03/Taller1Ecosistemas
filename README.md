# Taller1Ecosistemas

# Descripcion de componentes Squishy

## Eclipse / Pantalla de juego

### Main

Clase principal encargada de mostrar la interfaz grafica del juego, extiende de PApplet para asi obtener elementos de Processing

#### Logica

Clase encargada del mundo, donde se calcula la parte sistematica del juego, se utilizará el patrón Observer por lo que se implementará Observer 

**Atributos**

- gano: boolean (determina si el jugador gano el nivel de partida)

- nivel: int  (nivel de dificultad del juego -facil, medio, dificil-)

- pantalla: int (numero de pantalla de juego - inicio, instrucciones, ganada o perdida de la partida-)

- puntaje : int (puntaje ganado en la partida)

- tiempo: int (tiempo restante de la partida)

- camarones: ArrayList<Recogible> (arreglo indefinido de recogibles)

**Metodos**

- Logica(): Constructor
- pintar(): Dibuja la parte gráfica del juego
- cambioPantalla(): Realiza el cambio de pantalla dependiendo de lo que seleccione el usuario
- seleccionarNivel(): Se determina el nivel de juego dependiendo de lo que seleccione el usuario
- choque() : Validación de distancia entre el personaje y el ambiente
- validarCamaron(): Validación de distancia entre personaje y recogible (Camarón)
- update(): actualiza los datos recibidos por el control del usuario (android)


### Personaje

Clase dedicada a la informacion de personaje del juego, Squishy

**Atributos**

- img: PImage (imagen del personaje)
- x :  int  (posición x del personaje)
- y :  int  (posición x del personaje)


**Metodos**

- Personaje(): Constructor
- pintar():  Pinta el personaje
- mover() : Movimiento del personaje
- getX()  : Permite obtener la posición en x del personaje
- getY() : Permite obtener la posición en y del personaje



### Recogible

Clase dedicada a la información de los recogibles, los camarones

**Atributos**

- img: PImage (imagen del recogible)
- x :  int  (posición x del recogible)
- y :  int  (posición x del recogible)


**Metodos**

- Recogible(): Constructor
- pintar():  Pinta el recogible
- mover() : Movimiento del recogible
- getX()  : Permite obtener la posición en x del recogible
- getY() : Permite obtener la posición en y del recogible


### ControlJuego

Clase dedicada al intercambio de información entre la pantalla (eclipse) y el control (android), extiende de Observable e implementa Runnable

**Atributos**
- ss: ServerSocket
- s: Socket
- salida: DataOutputStream
- entrada: DataInputStream


**Metodos**

- ControlJuego()
- run()
- enviar()
- recibir()




## Android Studio / Control Usuario

### Pinicio

**Atributos**
- jugar: Button
- instruc: Button
**Metodos**
- OnCreate()
- update()

### Pinstrucciones

**Atributos**
- jugar
**Metodos**
- OnCreate()
- update()

### Pjuego

**Atributos**
- arriba:  Button
- abajo : Button
- derecha : Button
- izquierda : Button


**Metodos**
### Comunicacion
**Atributos**
- socket: Socket
- salida: DataOutputStream
- entrada: DataInputStream
- conectado: boolean
**Metodos**
