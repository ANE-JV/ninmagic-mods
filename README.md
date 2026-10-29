# NinMagic Mods 1.4.0

Aplicación homebrew para Nintendo Switch con Atmosphère. Busca mods publicados de gráficos, FPS, ropa y personajes en GitHub y GameBanana; permite elegirlos, instalarlos y retirar los archivos instalados por NinMagic.

## Qué cambia en 1.4.0

Se elimina el paso manual «Revisar archivo» y el bloqueo por datos de compatibilidad ausentes o diferentes. Un mod se puede elegir aunque el autor no indique versión de juego, falte una declaración de Switch física o el Build ID de la consola no esté disponible. «Disponible» significa que el formato se puede seleccionar, no que su funcionamiento esté comprobado.

Los archivos siguen comprobándose al prepararlos: descarga completa, hash, estructura, destino del juego y límites de tamaño. Los mods explícitamente exclusivos de emuladores permanecen excluidos. Las fuentes y formatos admitidos no cambian por esta actualización.

## Instalar la aplicación

Extrae el ZIP completo en la raíz de la microSD, conservando sus carpetas. Está preparado para extracción desde NinMagic AIO Updater o cualquier instalador que conserve las rutas del ZIP.

- `switch/NinMagicMods/NinMagic-Mods.nro`: aplicación.
- `switch/.overlays/ninmagic-mods.ovl`: complemento para un cargador de overlays ya instalado.
- `config/NinMagicMods/update-url.txt`: canal oficial de actualizaciones de esta aplicación.

NinMagic Mods funciona sin un cargador de overlays. El canal integrado es `https://raw.githubusercontent.com/ANE-JV/ninmagic-mods/main/update.txt`. En la biblioteca, **R** consulta actualizaciones; confirma la descarga y vuelve a abrir la aplicación al terminar. El NRO incluye el overlay correspondiente para actualizarlo al siguiente inicio.

## Instalar mods

1. Cierra el juego que vas a modificar. Abre NinMagic Mods en modo aplicación, por ejemplo manteniendo R al iniciar otro título.
2. Selecciona el juego con **A**. **X** en la biblioteca actualiza los catálogos Git; GameBanana se consulta para el juego elegido.
3. Pulsa **A** para marcar un mod. Si GameBanana ofrece varios ZIP/RAR, elige el archivo deseado. Un único archivo queda marcado al consultarlo.
4. Pulsa **Y** para descargar y preparar lo marcado. La aplicación valida los archivos automáticamente; no exige revisión manual ni coincidencia de versión del autor.
5. La pantalla de confirmación muestra la selección. Pulsa **A** para instalar y conservar los archivos anteriores.
6. Espera a que termine, cierra NinMagic y abre el juego.

**ZR** muestra la explicación, la versión indicada y el texto original del autor. Su versión del mod no se presenta como versión del juego. Los modelos y otros recursos RomFS requieren el juego cerrado. ZIP/RAR requieren modo aplicación por su uso de memoria; Álbum sigue admitiendo parches estáticos pequeños.

Los parches IPS/PCHTXT conservan su **Build ID objetivo del autor**. No se renombran a otro ejecutable para forzarlos: Atmosphère los carga cuando corresponde ese identificador. Si no coincide, puede no haber efecto. Ya no hace falta abrir el juego para autorizar su preparación desde la aplicación. No se modifica memoria en tiempo real.

Instala selecciones de IPS y RomFS por separado. No se combinan archivos que escriben contenido diferente en una misma ruta, parches con escrituras contradictorias ni parches de diferentes Build IDs en una única selección. En estos casos elige una variante. No se elige automáticamente entre alternativas dentro de un mismo archivo.

## Si el juego se cierra o el mod va mal

1. Cierra por completo el juego desde HOME. Si se cerró solo, déjalo cerrado.
2. Abre NinMagic Mods en modo aplicación mediante otro título.
3. Selecciona el juego y pulsa **L → Retirar**.
4. Confirma con **A**, espera al resultado y vuelve a abrir el juego.

La retirada elimina los archivos registrados como propios y restaura los originales guardados antes de la primera instalación de NinMagic. También funciona si el juego no llega a arrancar, sin necesitar leer su Build ID en ejecución. Una operación interrumpida se recupera mediante sus recibos y copias.

Conserva `config/NinMagicMods/backups/`: contiene las copias y recibos necesarios. Si otro programa cambió después un archivo, NinMagic lo señala y no lo sobrescribe silenciosamente. Los archivos de otros gestores y las partidas guardadas no se borran. Retirar un mod no deshace cambios que el propio juego ya haya guardado en una partida, ni soluciona problemas ajenos a esos archivos.

## Overlay

El ZIP incluye el overlay actualizado. Permite consultar y elegir parches estáticos pequeños para el juego abierto; se aplican después de reiniciar el juego. Los ZIP/RAR, modelos y operaciones grandes se completan en la aplicación. Consulta `Overlay.txt` para sus controles y límites. No se instalan recursos RomFS mientras el juego los está usando.

## Fuentes y descargas

Los mods se descargan directamente de GameBanana o de los repositorios originales. No hace falta crear un servidor propio y los paquetes de terceros no se redistribuyen dentro del ZIP de NinMagic.

El catálogo inicial contiene índices de tres repositorios, no todos sus archivos. La consulta de GameBanana está acotada a 90 publicaciones por juego en la app y 45 en el overlay, además de referencias destacadas; no representa todo su historial. Las fuentes y autores se conservan en cada entrada. La caché no garantiza disponer de todos los mods sin conexión.

## Formatos y límites

ZIP/RAR: hasta 128 MiB comprimidos o expandidos, 32 MiB por archivo y por diccionario RAR. La selección completa de recursos se limita a 128 MiB. Se rechazan rutas inseguras, enlaces, archivos corruptos o cifrados, paquetes divididos, mezclas ambiguas y formatos no admitidos.

7z, BCML/UKMM, ejecutables, plugins, cheats, sysmodules y paquetes que requieren herramientas o datos externos no se convierten automáticamente. NinMagic no modifica frecuencias, partidas ni archivos de arranque. Instalar un mod por elección del usuario no garantiza su efecto, rendimiento o ausencia de cierres.

## Compilar

Se necesitan devkitPro, devkitA64, libnx y las dependencias de los Makefiles. Ejecuta primero `bash tools/build-libarchive-switch.sh` desde devkitPro MSYS2 para compilar libarchive 3.8.10 con SHA-256 de origen fijado y zlib. El overlay no enlaza libarchive.

```powershell
.\tools\build-overlay.ps1 -ExpectedVersion 1.4.0
python tools/bundle_overlay.py
.\tools\build.ps1 -ExpectedVersion 1.4.0 -Preview
python tools/package.py
```

Se incluyen las fuentes y licencias correspondientes. Las pruebas del PC y la compilación no sustituyen una prueba física del efecto de cada mod.
