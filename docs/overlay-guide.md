# NinMagic Mods 1.4.1: overlay

El paquete instala `switch/.overlays/ninmagic-mods.ovl`. Se necesita un cargador de overlays compatible, como Ultrahand o Tesla. El paquete no cambia el cargador ni su combinación de botones.

1. Abre el juego y el menú de Ultrahand. Elige **NinMagic Mods**.
2. **X** consulta Git y GameBanana. **R** muestra el tipo, la fuente y los requisitos publicados por el autor.
3. **A** elige un parche estático. La lista muestra **ELEGIDO · SIN VERIFICAR**: elegirlo no comprueba su compatibilidad, ni lo instala todavía. Una versión o Build ID diferente o ausente no impide la elección.
4. **Y** obtiene los archivos y prepara la confirmación. Se conservan las comprobaciones de integridad, formato, rutas, tamaño y conflictos de archivos. **A** confirma escribir los IPS en la microSD.
5. **Cierra y vuelve a abrir el juego** para que Atmosphère cargue los parches que correspondan. El overlay no cambia la RAM del juego abierto ni adapta un parche a otra versión.

El nombre de destino IPS conserva el Build ID publicado por el autor. Permitir elegirlo no demuestra que se aplique al juego instalado. Un parche de otro Build ID puede no cargarse; un mod elegido puede no funcionar o cerrar el juego.

Desde 1.4.1, **INSTALADO** mantiene marcada la casilla a partir del registro de instalación y de sus archivos comprobados. **POR INSTALAR** indica una elección todavía pendiente. Pulsar **A** sobre un mod instalado no lo retira: para eso hay que cerrar el juego y usar **L → Retirar** en la aplicación. Las instalaciones antiguas que no guardaron nombres se indican como tales, sin atribuirles casillas concretas.

Los **ZIP/RAR y RomFS** indican **ABRIR EN APLICACIÓN**. Elige e instala esos paquetes desde NinMagic Mods; el overlay no los extrae ni descarga recursos de modelos. RomFS requiere el juego cerrado y modo aplicación. Los 7z y las dependencias no soportadas no se convierten automáticamente.

**Arriba/abajo** mueve la selección. **B** vuelve o esconde el panel. **ZL** cambia de lado. **ZR** guarda una elección opcional de parches para continuar en la aplicación. **L solo limpia esa cola**, conservando los mods instalados. **−** muestra ayuda. **+** sale al menú de overlays cuando termina la operación. Durante una consulta, **X** solicita cancelarla. Una transacción ya confirmada debe terminar antes de salir.

Para **retirar los mods instalados**, cierra el juego por completo y abre NinMagic Mods en modo aplicación. Selecciona el juego, entra en **Retirar** y confirma. La aplicación restaura las copias anteriores registradas y retira los archivos que ella añadió, siempre que sus recibos, hashes y copias sigan siendo válidos. Si otro programa cambió un archivo, no lo sobrescribe silenciosamente. No borres `config/NinMagicMods/backups/`. La retirada no revierte partidas guardadas ni cambios que el propio juego haya guardado.

El overlay mantiene el proceso, Title ID y contenido del juego que seleccionaste durante la preparación y confirmación. Si el proceso cambia, se descarta la confirmación pendiente; esto evita aplicar una selección a otro contexto. El Build ID leído del juego se muestra como información, y no se exige que coincida con el del mod para elegirlo.

La caché compacta contiene como máximo 128 resultados y 256 KiB. Guarda metadatos y elecciones, nunca permisos de instalación ni respaldos. Puedes elegir una entrada guardada; **Y** vuelve a consultar su fuente si todavía no se obtuvo una lista actual en esta sesión. Después se preparan los archivos antes de confirmar. No existe un paso separado de aprobación de compatibilidad.

Al pasar a 1.4.1, la lista antigua del overlay se vuelve a consultar con **X** una vez: esas listas no incluían los datos necesarios para excluir las herramientas de PC. Los mods instalados, sus copias y las elecciones guardadas se conservan.

Límites del overlay: 32 opciones, 128 KiB de archivos de parche y 8 KiB de escrituras estáticas combinadas. Conserva el control de memoria y su margen usando el heap real del cargador. Si una consulta no cabe, mantiene la lista anterior e indica que se use la aplicación. Los respaldos de otros tipos de mods se comprueban por bloques sin cargarlos completos en RAM. La reserva del cargador no se modifica.

## Código y atribuciones

La interfaz usa [libtesla de WerWolv](https://github.com/WerWolv/libtesla), distribuida bajo **GNU GPL v2 o posterior**. Se conserva su código y licencia en `overlay/deps/libtesla`. Su rasterizador usa `stb_truetype.h`, con la licencia incluida en ese mismo archivo. El código fuente correspondiente se distribuye con la aplicación.

El adaptador HTTPS nativo y el armazón de renderizado se adaptaron del proyecto NinMagic Cheats del mismo autor. Este overlay usa el espacio de nombres `nmm` y sus propios destinos y controles; no modifica la aplicación Cheats.

El logo y el icono son los recursos de **NinMagic Mods**. La licencia de la fuente incluida se conserva en `romfs/FONT-LICENSE.txt`. Los mods continúan perteneciendo a sus autores; el catálogo muestra las fuentes y no redistribuye paquetes de GameBanana.


En 1.4.1, una casilla **INSTALADO** se recupera del registro de instalación comprobado al abrir el overlay. No cuenta como nueva elección ni se retira al pulsar A. Para quitarla, cierra el juego y usa **L → Retirar** en la aplicación. Las nuevas elecciones se muestran **POR INSTALAR**. Limpiar la cola del overlay conserva los mods instalados.
