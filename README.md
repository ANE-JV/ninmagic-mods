# NinMagic Mods 1.2.1

Aplicación para Nintendo Switch con Atmosphère y overlay de Ultrahand/Tesla. Consulta mods publicados, explica sus efectos y prepara los archivos comprobados con copias anteriores y retirada reversible. Logo MODS y colores neón de NinMagic.

## Instalar y actualizar

El ZIP completo está preparado para la carpeta Herramientas del servidor de NinMagic AIO Updater. Se extrae en la raíz de la microSD, uniendo switch y config. La aplicación queda en `switch/NinMagicMods/NinMagic-Mods.nro` y el overlay en `switch/.overlays/ninmagic-mods.ovl`. La carpeta fuentes contiene el código correspondiente y no es necesaria para ejecutarlos.

Se necesita un cargador de overlays compatible ya instalado. El paquete no instala el cargador ni cambia su combinación de botones. Al abrir el NRO, verifica su overlay integrado y puede copiarlo o actualizarlo en su ruta propia, conservando copias anteriores.

R en la biblioteca comprueba el canal propio de actualización. A confirma una nueva descarga. El NRO se verifica por HTTPS, tamaño, SHA-256, nombre y versión; se conserva una copia anterior. Cierra y vuelve a abrir NinMagic después de actualizar, para ejecutar la nueva versión y renovar su overlay.

Canal independiente de Cheats, Cleaner y la web: `https://raw.githubusercontent.com/ANE-JV/ninmagic-mods/main/update.txt`. Una configuración HTTPS válida en `config/NinMagicMods/update-url.txt` puede sustituirlo. Un fallo de red no se presenta como confirmación de estar actualizado.

## Buscar y entender los resultados

A elige un juego. X en la biblioteca actualiza las fuentes Git; Y vuelve a leer la lista de juegos; L muestra las fuentes. Desde 1.2.1 se consultan solo fuentes que documentan Nintendo Switch física. La copia inicial muestra 284 opciones de formato admitido, obtenidas de tres fuentes, con distintas versiones y duplicados; cada resultado debe superar además las comprobaciones aplicables a tu juego. Los archivos comprimidos y los formatos que la aplicación no instala se excluyen de la lista.

El catálogo excluye los mods de emulador, los de destino sin confirmar y los que solo documentan pruebas en emulación. La política también se aplica a las cachés y selecciones antiguas, y se vuelve a comprobar antes de preparar archivos. Tener procedencia para Switch física no convierte un Build ID o una versión distintos en compatibles.

ZR abre el detalle de un mod. Explica en español los efectos conocidos y conserva el nombre original. X dentro del detalle muestra el texto del autor. No se inventan explicaciones para nombres desconocidos. X en la lista alterna entre todos los resultados y los compatibles.

GameBanana deja de consultarse en esta versión: sus fichas no acreditan aquí el destino físico y la compatibilidad necesarios. No se incluyen entradas de emulador ni fichas de destino desconocido para aumentar artificialmente los resultados. La versión del mod nunca sustituye a la versión del juego.

## Preparar parches de FPS o gráficos con el juego abierto

Los parches estáticos PCHTXT e IPS necesitan el Title ID y el Build ID completo de 32 bytes del juego real. Se obtiene del módulo en ejecución mediante el cargador, junto con su PID exacto. No se intenta inventarlo a partir de la versión visible ni de un archivo de cheats.

1. Abre el juego real que quieras modificar.
2. Déjalo abierto y abre NinMagic Mods desde Álbum, o usa su overlay.
3. Busca sus mods. A marca únicamente opciones que coincidan y tengan formato admitido.
4. Y prepara la revisión; A confirma guardar los archivos para el próximo inicio.
5. Espera a que termine. Después cierra el juego por completo desde HOME y vuelve a abrirlo.

La operación escribe únicamente archivos IPS propios en la microSD. No cambia la memoria ni el efecto de la partida que sigue abierta. El cargador aplica el archivo cuando vuelve a cargar un módulo con ese Build ID completo. Los identificadores y la identidad del contenido se comprueban otra vez durante la transacción; si cambia el PID o la identidad, no se continúa escribiendo.

Un acceso de HOME que pida cerrar el juego no sirve para comprobar su proceso vivo; utiliza Álbum o el overlay. Abrir hbmenu con R sobre el propio juego tampoco demuestra que ese juego esté ejecutándose: el proceso puede ser hbmenu/NinMagic, y se rechaza como prueba.

## Instalar modelos y otros recursos RomFS con el juego cerrado

Los recursos no contienen direcciones de código. Se exige Title ID correcto, versión del juego explícitamente declarada y coincidente, y una identidad del contenido instalado obtenida de NCM que no haya cambiado. No se afirma que un recurso tenga el Build ID de un ejecutable cerrado que no se ha podido leer.

1. Cierra el juego objetivo por completo.
2. Abre hbmenu en modo aplicación manteniendo R al iniciar OTRO juego, o utiliza un acceso de homebrew adecuado.
3. Selecciona el juego objetivo y marca sus recursos compatibles.
4. Y descarga/verifica y presenta la revisión. A confirma la instalación.
5. Cierra NinMagic y abre el juego.

El modo Álbum no instala archivos RomFS. No se mezclan parches de código y RomFS en una misma operación: requieren estados distintos del juego. Una selección nueva conserva los archivos propios del otro tipo de mod y sus respaldos; preparar un IPS no retira modelos RomFS mientras juegas.

Los paquetes ZIP/RAR/7z y los que requieren BCML, UKMM, datos del juego, plugins, merges u otras herramientas no se convierten en una copia RomFS compatible por tener un nombre parecido. Tampoco se interpretan Any, latest o la ausencia de versión como una versión del juego verificada.

## Overlay

El overlay detecta el juego abierto y consulta las fuentes sin buscar valores en RAM. Permite revisar y preparar parches estáticos pequeños para el siguiente inicio. Mantiene límites de memoria, respuestas y escrituras; los modelos, paquetes grandes y operaciones no admitidas se revisan en la aplicación.

La versión 1.2.1 corrige la comprobación de memoria del overlay: la ausencia del descriptor de heap HBABI no significa que el cargador no haya proporcionado un heap válido. El presupuesto se calcula con el rango real del allocator y sus contadores, conservando un margen de memoria. Si una consulta no cabe, informa de las cifras en KiB. No cambia la configuración ni la reserva del cargador.

Esta versión no incorpora un importador RAR/ZIP/7z. Los paquetes comprimidos y las fichas de formato no admitido quedan fuera de la lista, aunque su fuente documente hardware físico. Para comprobar los parches PCHTXT/IPS admitidos, deja el juego abierto y pulsa X en el overlay.

Los controles y límites exactos están en `Overlay.txt` y `docs/overlay-guide.md`. Esconderlo permite seguir jugando; salir a otro overlay descarga su proceso. No hay activación instantánea en memoria: reinicia el juego después de preparar sus parches.

## Retirar y recuperar

Cierra el juego objetivo. Abre NinMagic en modo aplicación mediante otro título, selecciona el objetivo y pulsa L en su lista. A confirma la retirada. Solo se retiran/restauran rutas registradas cuyos hashes y copias se puedan comprobar.

Las copias y recibos se conservan en `config/NinMagicMods/backups/`. No borres esa carpeta si quieres poder recuperar el estado anterior. Si otro programa cambió un archivo, no se sobrescribe silenciosamente. Un registro interrumpido requiere un contexto cerrado verificado para su recuperación.

Si cambias una selección por otra, retirar recupera los archivos originales conservados antes de los mods propios de NinMagic; no vuelve a activar la selección anterior. No borra ni edita partidas, ni revierte cambios que el propio juego ya guardó dentro de ellas. Los parches activos en un proceso anterior requieren cerrar y volver a abrir el juego para dejar de hacer efecto.

## Comprobaciones y límites

La coincidencia de identidad y el formato admitido no certifican el efecto del mod ni evitan todos los cierres. Los mods de emulador y de destino desconocido se excluyen del catálogo. La declaración del autor para Switch física no equivale a una prueba de NinMagic en esa consola. La aplicación no modifica frecuencias, cheats, sysmodules ni archivos de arranque.

Esta versión corrige el método que bloqueaba todos los parches al intentar leer ejecutables cerrados mediante fsp-ldr, un servicio con una sesión reservada al cargador. También retira el uso inválido del tipo Code en la API general de FS. Las pruebas del PC y de wrappers no sustituyen la comprobación en una consola real.

La caché permite consultar datos sin Internet y preparar archivos ya descargados y verificables; no garantiza tener todos los mods disponibles sin conexión. Las fuentes, autores y restricciones se detallan en Fuentes.txt.

## Compilar

Con devkitPro, devkitA64, libnx y las dependencias indicadas en los Makefiles:

```powershell
.\tools\build-overlay.ps1 -ExpectedVersion 1.2.1
python tools/bundle_overlay.py
.\tools\build.ps1 -ExpectedVersion 1.2.1 -Preview
python tools/package.py
```

Se distribuye el código fuente correspondiente y las licencias de las dependencias. Los archivos de mods de terceros no se incluyen en el ZIP de la aplicación.
