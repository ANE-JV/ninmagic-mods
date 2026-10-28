# NinMagic Mods 1.2.0: overlay

El paquete instala `switch/.overlays/ninmagic-mods.ovl`. Se necesita un cargador de overlays compatible, como Ultrahand o Tesla. El paquete no cambia el cargador ni su combinación de botones.

1. Abre el juego y el menú de Ultrahand. Elige **NinMagic Mods**.
2. **X** consulta Git y GameBanana para el proceso abierto. **R** muestra fuente, tipo y requisitos. Los destinos de emulador o desconocidos se conservan para probar y se indican en la revisión; no se presentan como probados en consola.
3. **A** marca parches compatibles. **Y** vuelve a preparar los archivos pequeños, comprueba los conflictos y muestra la revisión. **A** confirma la escritura del IPS en la microSD. Su nombre contiene el Build ID completo comprobado.
4. **Cierra y vuelve a abrir el juego**: Atmosphère carga ese IPS durante el siguiente inicio. Guardar un IPS no modifica la memoria del juego que ya está abierto.
5. Los modelos y paquetes **RomFS** se instalan desde la aplicación en modo aplicación con el juego cerrado. Exigen Title ID y versión declarados coincidentes, además de contenidos instalados comprobados. Para retirar mods usa también la aplicación con el juego cerrado; después reinicia el juego para que desaparezca el efecto de un IPS.

**Arriba/abajo** mueve la selección. **B** vuelve o esconde el panel para jugar. **ZL** cambia de lado. **ZR** guarda una selección opcional para revisar en la aplicación; los IPS necesitan que el juego siga abierto cuando la abras desde Álbum. **L** limpia esa cola, conservando los mods instalados. **−** muestra ayuda. **+** sale al menú de overlays cuando termina la operación. Durante una consulta, **X** solicita cancelarla. Una transacción ya confirmada debe terminar antes de salir.

El overlay no hace búsquedas de RAM ni escribe memoria del juego. Solo prepara IPS/IPS32 para el siguiente inicio y conserva copias y recibos. Cada escritura revalida el PID, el Build ID completo y los contenidos actuales; si cambian, bloquea la confirmación o conserva un registro de recuperación. Los archivos ajenos modificados no se sobrescriben durante la retirada. Un IPS de NinMagic nunca se renombra para otra versión.

La revisión comprueba identidad y conflictos estáticos; no demuestra que el autor haya probado el efecto en esa consola. Las entradas con datos de compatibilidad ausentes siguen bloqueadas. La versión del paquete GameBanana describe el mod, no la versión del juego. Los ZIP/RAR de GameBanana siguen bloqueados: la aplicación puede mostrar su ficha, pero actualmente no los extrae ni instala. También se bloquean las dependencias no soportadas.

Límites del overlay: 128 resultados, 32 opciones, 128 KiB de archivos de parche y 8 KiB de escrituras estáticas combinadas. Los modelos no se descargan desde él. Los respaldos de otros dominios se verifican y conservan por bloques sin cargarlos completos en RAM. Si un parche o respaldo individual excede el límite del overlay, indica que se use la aplicación.

La caché compacta tiene 256 KiB como máximo. Una lista antigua sin huella de contenidos se invalida. Los IDs de una cola no autorizan una instalación: se vuelven a comprobar los archivos, el contexto y el Build ID. Una lista guardada necesita **X** para volver a habilitar parches en el proceso actual. La reserva de memoria del cargador no se modifica; si falta memoria, se conserva la caché y se indica que se use la aplicación.

## Código y atribuciones

La interfaz usa [libtesla de WerWolv](https://github.com/WerWolv/libtesla), distribuida bajo **GNU GPL v2 o posterior**. Se conserva su código y licencia en `overlay/deps/libtesla`. Su rasterizador usa `stb_truetype.h`, con la licencia incluida en ese mismo archivo. El código fuente correspondiente se distribuye con la aplicación.

El adaptador HTTPS nativo y el armazón de renderizado se adaptaron del proyecto NinMagic Cheats del mismo autor. Este overlay usa el espacio de nombres `nmm` y sus propios destinos y controles; no modifica la aplicación Cheats.

El logo y el icono son los recursos de **NinMagic Mods**. La licencia de la fuente incluida se conserva en `romfs/FONT-LICENSE.txt`. Los mods continúan perteneciendo a sus autores; el catálogo muestra las fuentes y no redistribuye paquetes de GameBanana.
