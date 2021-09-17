Extrayendo datos acerca del videojuego League of Legends videogame utilizando la API de Riot Games
###Introduction

League of Legends, comúnmente conocido como LOL es un videojuego multijugador de arena de batalla en línea(MOBA por sus siglas en ingles) desarrollado y publicado por riot games.En el juego, dos equipos de 5 jugadores luchan en un combate de jugador vs jugador (PVP), cada equipo ocupa y defiende su respectiva mitad del mapa, los equipos se identifican de la siguiente manera

  •	Equipo Azul: Se ubican en la parte inferior izquierda del mapa.
  •	Equipo Rojo: Se ubican en la parte superior de derecha del mapa.
  
Cada jugador controla un personaje conocido como “Campeón”, con habilidades únicas y diferentes estilos de juego.
Durante la batalla, los campeones se van haciendo mas poderosos conforme avanza el tiempo de acuerdo a la experiencia, oro. La experiencia aumenta de manera automática las estadísticas base de cada campeón conforme se sube de nivel (Maximo nivel 18). El oro aumenta las estadísticas de los campeones invirtiendo este mismo en objetos que cuentan con diferentes características, las cuales benefician de manera diferente a casa campeón.

En el mapa principal llamado “La Grieta del Invocador” un equipo gana avanzando sobre el area del equipo rival y destruyendo su Nexo, que es una estructura localizada lejos del equipo del contrario.

![image](https://user-images.githubusercontent.com/82690716/133826558-d8f005ca-206f-4030-acc5-b3fcfd35cdfe.png)

 
Ahora que conocemos un poco acerca del juego podemos entender que una partida de este genera demasiada información y esta podemos extraerla de la API de RIOT.

La API de RIOT es una REST API que provee la información relacionada con los siguientes puntos:
•	Detalles del Jugador: nombre, nivel, icono de perfil, ID de cuenta.
•	Historial de coincidencias y detalles y líneas de tiempo de coincidencias por nombre de invocador.
•	La información actual del juego de alguien, si hay alguien en el juego.
•	Toda la estadística que se crea dentro del juego como: Cantidad de oro obtenido, primera sangre(primera baja de un jugador a otro), primera torre derribada, que hechizos de invocador se utilizaron, 

##Requisitos Previos

Los siguientes requisitos deben completarse antes de empezar a utilizar la API de RIOT.

•	Darse de alta en el sitio para desarrolladores de Riot con el fin de obtener una API Key. Sugiero leer la documentación, así como las políticas de la misma para saber los alcances y limitaciones al hacer uso de la misma.
•	Python instalado en tu maquina.
•	Instalar la librería Riot Watcher.
Obteniendo nuestra API key
Para obtener una API key necesitamos darnos de alta en el sitio de desarrolladores de Riot:
 
1.- Estando en esta parte del sitio Web seleccionamos la opción SIGN UP NOW
    
2.- Se te solicitara una cuenta de correo electronico para registrarte en el sitio.

3.- Se te solicitara tu fecha de nacimiento para la creacion de tu cuenta. Tu edad debe ser igual a mayor a 13 años.

4.- Debes elegir tu nombre de usuario

5.- Capturas tu contraseña.
 
Una vez terminado el proceso en tu perfil se te mostrara de manera oculta tu API key la cual se utilizara para extraer la información de la API.

Extrayendo los datos

Instalamos la librería de riotwatcher para poder empezar a extraer los datos de la API:

Antes de proceder con el uso de riotwatcher debemos tomar en cuenta que hay mucha info estática que provee la web de RIOT que no viene incluida en la librería, pero que puede ser extraída con un request GET al endpoint de la API en formato JSON, si bien no es informacion que vaya a manejar durante este escrito creo que es importante que se conozca.
A continuación ejemplos de la información estática:

•	Seasons: Nos ayuda a identificar en que season se jugo el match.
•	Colas de Juego: dentro del juego hay tipos de cola de espera para entrar a una partida, las mas comunes son: partida normal, clasificatoria en solitario y clasificatoria flexible.
•	Modos de Juego: a lo largo de sus casi 11 años ha habido mucho modos de juegos en league of legend de los cuales destacan: URF, Uno para todos, ARAM, por mencionar algunos.
•	Mapas: Identifica en que mapa se jugo el match, ejemplos: Abismo de los lamentos, grieta del invocador, bosque retorcido.

Primero que nada para hacer la conexión con la API ejecutamos el siguiente código:

Para el desarrollo de este escrito extraeré los datos de mi cuenta personal: “SquareHammer”.
Ejecutamos el siguiente del cual obtendremos su perfil de invocador y


