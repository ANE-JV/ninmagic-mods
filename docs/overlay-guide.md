# NinMagic Mods 1.1.0: overlay

El paquete instala `switch/.overlays/ninmagic-mods.ovl`. Se necesita un cargador de overlays compatible, como Ultrahand o Tesla. El paquete no cambia el cargador ni su combinación de botones.

1. Abre el juego y el menú de Ultrahand. Elige **NinMagic Mods**.
2. **X** consulta los índices Git y GameBanana para el juego abierto. Una lista previamente revisada por la aplicación también se puede leer sin Internet. Los resultados muestran su categoría y compatibilidad.
3. **R** muestra la fuente, los requisitos de versión o Build ID y el motivo de un bloqueo. La versión del paquete de GameBanana describe el mod; no demuestra la versión del juego.
4. **A** marca un mod compatible; vuelve a pulsarlo para desmarcar. **Y** revisa la selección y **A** la guarda. Hasta 32 opciones quedan pendientes para el Title ID, versión, contenido y Build ID completos de ese juego.
5. Cierra el juego y abre la aplicación **NinMagic Mods**. Busca sus mods, revisa la selección pendiente y confirma la instalación. La aplicación vuelve a comprobar la identidad, las descargas y los conflictos. Para retirar mods, usa también la aplicación con el juego cerrado.

**Arriba/abajo** mueve la selección. **B** vuelve a la lista o esconde el panel para jugar. **ZL** cambia el lado del panel. **L** borra únicamente la selección pendiente; conserva los mods ya instalados. **−** muestra ayuda. **+** sale al menú de overlays cuando la operación haya terminado. Durante una consulta, **X** pide cancelarla; espera a que termine antes de salir.

El overlay prepara una selección. No escribe parches ni archivos RomFS en Atmosphère mientras el juego está abierto. No modifica memoria del juego, ejecuta cheats, descarga modelos ni hace búsquedas de RAM. La compatibilidad declarada se comprueba contra los datos publicados y la identidad del juego; no equivale a una prueba de funcionamiento realizada en esa consola.

Los paquetes de modelos y RomFS se revisan desde la aplicación. El overlay admite como máximo 128 resultados, parches de 128 KiB y 8 KiB de escrituras estáticas; los paquetes mayores permanecen bloqueados y muestran el motivo. La caché compacta ocupa como máximo 256 KiB. Una selección guardada de otra versión o Build ID se rechaza. El contenido recibido de una fuente no puede autorizar por sí solo una instalación.

Las consultas en Internet requieren HTTPS. La caché se guarda en `config/NinMagicMods`, separada de las partidas y los mods instalados. No se modifica la reserva global de memoria del cargador. Si no hay suficiente memoria para una consulta, el overlay indica que se use la aplicación.

## Código y atribuciones

La interfaz usa [libtesla de WerWolv](https://github.com/WerWolv/libtesla), distribuida bajo **GNU GPL v2 o posterior**. Se conserva su código y licencia en `overlay/deps/libtesla`. Su rasterizador usa `stb_truetype.h`, con la licencia incluida en ese mismo archivo. El código fuente correspondiente se distribuye con la aplicación.

El adaptador HTTPS nativo y el armazón de renderizado se adaptaron del proyecto NinMagic Cheats del mismo autor. Este overlay usa el espacio de nombres `nmm` y sus propios destinos y controles; no modifica la aplicación Cheats.

El logo y el icono son los recursos de **NinMagic Mods**. La licencia de la fuente incluida se conserva en `romfs/FONT-LICENSE.txt`. Los mods continúan perteneciendo a sus autores; el catálogo muestra las fuentes y no redistribuye paquetes de GameBanana.
