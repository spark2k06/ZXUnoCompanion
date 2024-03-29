Release 4 Reloaded (25/09/2021) 
-------------------------------

* Se ha corregido la interceptación de algunos símbolos que faltaban en algunos cores con la combinación SS+, sobre todo de la primera fila del teclado (1,2,...), fallos introducidos cuando comencé con la rama alternativa, por tanto, la rama original no tiene estos fallos.

* Se han añadido nuevos símbolos a varios modos de teclado ya existentes.

* Se ha añadido soporte de modos de teclado a los siguientes cores:

	* Acorn Atom
	* Acorn Electron
	* ZX80
	* ZX81
	* EACA Colour Genie
	* Camputers Lynx
	* Elan Enterprise

Gracias @desUBIkado por la ayuda en la identificación de los nuevos símbolos, tanto para los modos de teclado ya implementados como para los nuevos. También por hacer de betatester en el firmware de ZXUnoPS2, firmware en el que está basado éste.

Release 3 (26/09/2020)
----------------------

* Release final
* Migracion al nuevo sistema de ZXUnoPS2 alternativo
* Los atajos especiales de Sugarless pasan a ser los siguientes:

	* CS + SS + F -> T: TZXDUINO ON / OFF
	* CS + SS + F -> Q: XCHG CURSORS KBPC ON / OFF
	* CS + SS + F -> W: XCHG DEL BREAK ON / OFF
	* CS + SS + F -> J: Famicom <-> Atari/Megadrive

Release 2 (12/01/2019) -> Basada en la version original de ZXUnoPS2
-------------------------------------------------------------------

* Compatibilidad con gamepads famicom en Joy2PS2 mediante atajo (Extra+U -> J)
* Extra+H -> Keypad - (C64, C16, Atari 800XL, BBC Micro y Apple II: Scanlines)
* Extra+M -> Keypad * (Atari 800XL: PAL/NTSC)

Al hacer el atajo de Extra+U -> J, pasará de famicom a atari/megadrive y viceversa, mostrándose por pantalla ".JOY FAMICOM" ó ".JOY ATARISMD" y guardando la configuración en la EEPROM, de manera que la última selección se encontrará disponible en siguientes arranques. 

Release 1.1 (14/05/2018)
------------------------

* Con el control del tzxduino activado, entra en juego una nueva combinacion: EDIT

- EDIT habilita el control del teclado con Cursores/Enter inhabilitando el control de tzxduino y viceversa. Necesario para controlar temporalmente ciertos cores como el spectrum cuando el control del tzxduino se encuentra activo.

Release 1 (09/05/2018)
----------------------

* Unificacion de configuraciones en atmega128 y atmega2560 mediante el uso de la EEPROM, ahora solo tenemos un archivo por AVR.

* Activacion/Desactivacion de modo TZXDuino mediante atajo (Extra+U -> T). Controles: UP, DOWN, ENTER (PLAY/PAUSE), RIGHT (STOP/END), LEFT (ROOT)

* Intercambio de teclas Borrar y Break mediante atajo (Extra+U -> O), se guarda la configuracion en la EEPROM.

* Intercambio de teclas de cursor mediante atajo (Entra+U -> P), se guarda la configuracion en la EEPROM.

* Ahora con la EEPROM sin inicializar, por defecto el modo de teclado en el mapa .ZX es .ZXFULLCOMBOS en lugar de .ZXPARTIALCOMBOS para evitar confusiones y que inicialmente esten disponibles todos los atajos.

Beta 5
------

-> Correcciones relativas al control del tzxduino.

-> Modificacion de tipos de variables propuesto por yombo para su correcta compilacion en entorno IDE de arduino.

-> Bajada de tiempo necesario manteniendo el boton de reset pulsado para apagar el ZX-Uno.

Beta 4
------

-> Comportamiento de los botones select y start igual que el resto de botones, se pulsan y mantienen pulsados hasta que son soltados. El uso anterior tenia sentido en la versión original de Joy2PS2 ya que estos botones también se usaban para realizar ciertos combos, pero ya no es necesario al disponer de un teclado siempre conectado.

Beta 3
------

-> 100 ms de delay tras la pulsacion de start y select en el puerto joy2ps2 para que le de tiempo a procesarlo al ZX-Uno.

Beta 2
------

-> Cambio de control de TZXDUINO a EXTRA + U y GHJKL para no entrar en conflicto con B y C en el cambio de layout de teclado.

Beta 1
------

-> Primera versión beta con un funcionamiento muy básico pero con todas las características principales disponibles.

Alpha 4
------

-> Nueva mejora de la gestión de combos para evitar la repetición de sus teclas asociadas a la función seleccionada.

Alpha 3
------

-> Se incluye una versión simplificada del proyecto Joy2PS2 para el segundo puerto de Joystick de Sugarless +2, sin posibilidad de redefinición de teclas por el momento:

	KEY_Q,        // UP
	KEY_A,        // DOWN
	KEY_O,        // LEFT
	KEY_P,        // RIGHT
	KEY_5,	      // SELECT
	KEY_1,	      // START
	KEY_SPACE,    // BUTTON 1
	KEY_X,        // BUTTON 2
	KEY_M,        // BUTTON 3
	KEY_D,        // BUTTON 4
	KEY_F,        // BUTTON 5
	KEY_C         // BUTTON 6

-> Nuevos modos de teclado (.PC, .PCXT, .KBEXT)

-> Código configurable en tiempo de compilación para poder intercambiar las teclas "Break" y "Borrar" y/o cursores por "." y "," (proximamente se podrá hacer mediante atajo, quedando guardada la configuración en la EEPROM de forma permanente)

-> Mejora de la gestión de combos para evitar la repetición de sus teclas asociadas a la función seleccionada.

Alpha 2
------

Mejora en la gestión del encendido/apagado + reset físico. Ahora para apagar se requiere que esté pulsado 3 segundos el boton de reset, de lo contrario se producirá un reset físico. 

Alpha 1
------

-> Se incluye el proyecto original ZXUnoPS2, adaptado a los AVR atmega128 y atmega2560.

-> Gestión de encendido/apagado del ZX-Uno conectado a Sugarless +2.

-> Gestión de bidireccionalidad del puerto PS/2 externo de Sugarless +2.
