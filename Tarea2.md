# **Tarea2**

**Ejercicio 1 - exercise1.txt**

Como primer paso verificamos con el comando **file** el tipo de archivo en donde podemos observar que se trata de un archivo wav.

* cd Descargas/tarea2
* file exercise1.txt

> exercise1.txt: RIFF (little-endian) data, WAVE audio, Microsoft PCM, 16 bit, mono 44100 Hz

Reproducimos el audio notamos que son tonos y asumimos que es codigo morse.

Lo cargamos en la siguiente plataforma:

[https://morsecode.world/international/decoder/audio-decoder-adaptive.html](https://morsecode.world/international/decoder/audio-decoder-adaptive.html)

seleccionamos y subimos el archivo y obtenemos el mensaje oculto que es:

***El sonido es el tacto a distancia del alma***

![Obteniendo el mensaje oculto](https://github.com/steckmera/downloads/blob/main/02.png)


**Ejercicio 2 - exercise2.tar.gz**

Como primer paso verificamos con el comando **file** el tipo de archivo en donde podemos observar que se trata de un archivo gif.

* cd Descargas/tarea2
* file exercise2.tar.gz

> exercise2.tar.gz: GIF image data, version 89a, 348 x 270

Adicionalmente con la herramienta exiftool para consultar metadatos podemos ver que la imagen se creó con el software GIMP y que tiene un total de 99 frames.

Abrimos la imagen con GIMP y comenzamos a revisar cada FRAME y en el FRAME 91 observamos un texto procedemos hacer zoom a 800% y observamos el mensaje oculto que es:

***A LA GRANDE LE PUSE CUCA***

![Obteniendo el mensaje oculto](https://github.com/steckmera/downloads/blob/main/03.png)


**Ejercicio 3 - exercise3.wav**

Como primer paso verificamos con el comando **file** el tipo de archivo en donde podemos observar que se trata de un archivo de texto.

* cd Descargas/tarea2
* file exercise3.wav

> exercise3.wav: ASCII text

* nano exercise3.wav

Analizando el contenido del archivo podemos observar que está codificado en base64 procedemos a decodificarlo.

* base64 -d exercise3.wav > output.txt
* nano output.txt

Viendo el contenido del archivo output.txt observamos el magic number que es un ELF (bincaro), procedemos a renombrarlo y darle permisos de ejecucion y lo ejecutamos.

* mv output.txt output.bin
* chmod +x output.bin
* ./output.bin

y nos muestra el mensaje oculto que es:

**La basura de un hombre es el tesoro de otro**


**Ejercicio 3 - exercise4.mp3**
Como primer paso verificamos con el comando **file** el tipo de archivo en donde podemos observar que se trata de un archivo gba (una room de game boy).

* cd Descargas/tarea2
* file dontstartnow.mp3

> dontstartnow.mp3: Game Boy Advance ROM image: "GBA" (000000, Rev.00)

Procedemos a revisar los strings

* strings dontstartnow.mp3 > output.txt
* nano output.txt

Revisando el contenido nos centramos en el contenido de las ultimas lineas y utilizamos la herramienta CyberChef

[https://gchq.github.io/CyberChef](https://gchq.github.io/CyberChef)

Aplicamos XOR({'option':'Hex','string':'5a'},'Standard',false)

Al siguiente texto:

> 0/=;4>5z7;(35z?4z6/=;(z>?z2;9?(z?6z>?8?(z>?z957*/.;9354z<5(?4)?

Obtenemos el mensaje oculto que es:

**jugando mario en lugar de hacer el deber de computacion forense**

Tambien obtuvimos el mensaje cargando la room en un emulador de Game Boy VBA-M | VisualBoyAdvance-M 2.1.9

![Obteniendo el mensaje oculto](https://github.com/steckmera/downloads/blob/main/04.png)