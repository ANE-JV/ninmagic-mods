# NinMagic Mods 1.0.0

Aplicación NRO para Nintendo Switch con Atmosphère. Catálogo de mods publicados, comprobación de identidad y versión, selección e instalación con copias anteriores y retirada reversible. Interfaz en español con colores neón y el logo de NinMagic adaptado con la marca MODS en magenta y violeta.

## Descargar e instalar

El ZIP completo se puede alojar en la carpeta Herramientas de tu servidor para descargarlo con NinMagic AIO Updater. Extrae en la raíz de la microSD, uniendo `switch` y `config`.

El ejecutable debe quedar en `switch/NinMagicMods/NinMagic-Mods.nro`. Los índices y la configuración quedan en `config/NinMagicMods/`. Las fuentes correspondientes están dentro de `fuentes/` y no son necesarias para ejecutar la aplicación.

Abre hbmenu en modo aplicación manteniendo R al iniciar otro juego o usando un acceso de homebrew compatible. El título que sirve para abrir hbmenu no se puede considerar cerrado para modificarlo; usa otro título. El modo Álbum/applet permite consultar, pero bloquea la instalación y retirada de mods.

## Elegir e instalar

1. Selecciona un juego de la biblioteca con A.
2. Se comprueban el Title ID, la versión y el Build ID completo del ejecutable efectivo. Si tiene una actualización instalada, no se usa el identificador de la base antigua.
3. Los resultados muestran categoría, fuente, compatibilidad y motivo de bloqueo. X alterna entre todos y los compatibles. A solo marca opciones compatibles.
4. Con el juego cerrado, Y descarga y verifica la selección para revisarla. Si ya hay archivos en sus destinos, se informa antes de sustituirlos.
5. A confirma la instalación. La identidad del juego y los archivos se vuelven a comprobar; se conservan copias de los archivos anteriores.
6. Cierra la aplicación y abre el juego para que Atmosphère cargue los mods.

El catálogo contiene categorías de gráficos, FPS, ropa y personajes. La disponibilidad depende de cada juego y versión; no se inventan opciones. Las diez fuentes iniciales incluyen 3.420 resultados de archivos o grupos, con duplicados de versiones y resultados bloqueados. Esa cifra no representa mods instalables en todos los juegos.

## Compatibilidad estricta

Los parches estáticos PCHTXT e IPS/IPS32 requieren el Title ID correcto y el Build ID completo de 32 bytes coincidente con el ejecutable instalado. Se comprueban también las versiones expresas de los autores cuando están declaradas. Un nombre parecido nunca autoriza la instalación.

Los mods RomFS requieren Title ID exacto, una versión explícita que coincida y una fuente que documente hardware Switch. No se interpreta Any, latest ni la ausencia de versión como compatibilidad. Un Build ID recortado solo se puede completar con ceros según la regla de Atmosphère y debe coincidir con los 32 bytes, nunca solo con un prefijo.

El instalador rechaza archivos incompatibles, rutas fuera de sus destinos, conflictos entre mods, parches externos para el mismo ejecutable y archivos que cambien después de la revisión. No instala cheats, plugins NRO, sysmodules, archivos de arranque, configuraciones de overclock ni guardados.

La coincidencia de identidad y el formato correcto reducen el riesgo, pero no certifican el efecto del mod ni evitan todos los cierres. Algunos autores exigen requisitos concretos de hardware o frecuencias; la aplicación no cambia las frecuencias. Conserva las condiciones del autor.

## Qué puede instalar esta primera versión

Se admiten parches estáticos comprobados y grupos RomFS publicados con identidad y versión inequívocas. Los ZIP/RAR/7z y los paquetes dependientes de otras herramientas se muestran para consulta cuando se identifica el juego, pero no se extraen como si su nombre demostrara compatibilidad.

La ropa identificada en las fuentes iniciales incluye cinco variantes publicadas de Zelda Hood Down para Echoes of Wisdom. Esto no equivale a una colección general de modelos de otros personajes.

Los modelos de personajes externos que requieren BCML, UKMM, archivos del juego, DLC o una mezcla de recursos no se pueden instalar como una copia RomFS simple. No se incluyen ni se preparan automáticamente sin esos datos. La fuente de Linkle incluida es una referencia de diálogos chinos, no el modelo del personaje; permanece bloqueada por sus requisitos y versión sin verificar. Estas limitaciones se explican en la lista y en Fuentes.txt.

## Retirar mods y recuperar archivos

Selecciona el juego y pulsa L. Con el juego cerrado se revisan los mods registrados y A confirma su retirada. Se recuperan los archivos anteriores verificados o se retiran únicamente los archivos nuevos añadidos por NinMagic Mods.

Las operaciones conservan recibos y copias por juego dentro de `config/NinMagicMods/backups/`. Si un archivo fue cambiado después por otra aplicación, no se sobrescribe silenciosamente: la operación se bloquea para conservar los datos y sus copias. Una operación interrumpida deja un registro que se comprueba para recuperar únicamente sus archivos propios.

Si una selección reemplazó otra selección anterior, la retirada recupera el estado anterior registrado. Los cambios que el propio juego haya guardado dentro de una partida no se revierten al restaurar archivos del mod. La aplicación no borra ni edita partidas.

## Catálogo y fuentes

X en la biblioteca fuerza la actualización de las fuentes. Y vuelve a leer los juegos. Al elegir un juego se comprueban y descargan los candidatos necesarios, verificando su tamaño y hash Git original. El paquete trae índices iniciales para consultar sin red; no incluye los archivos de los mods de terceros.

La caché reciente se reutiliza durante seis horas. Si falla una fuente, se informa y se conserva su índice verificado. Un fallo de conexión no se presenta como prueba de que un juego no tenga mods. La página GitHub Topics: switch-mods sirve para descubrir repositorios, no como fuente instalable por sí misma.

Las fuentes y sus limitaciones se documentan en `Fuentes.txt` y `docs/sources.md`. Cada autor conserva sus derechos y enlaces de procedencia. Las descargas van desde los repositorios originales al caché privado de la consola.

## Actualizar NinMagic Mods

R en la biblioteca consulta el canal propio de la aplicación. Se comprueba también al abrir. Si hay una nueva versión, A confirma la descarga y la instalación tras verificar HTTPS, tamaño, SHA-256, estructura, nombre y versión del NRO. Se guarda una copia de la aplicación anterior. Después cierra NinMagic Mods y vuelve a abrirla.

El canal oficial está integrado en el NRO y separado de Cheats, Cleaner y la página web:

`https://raw.githubusercontent.com/ANE-JV/ninmagic-mods/main/update.txt`

El archivo opcional `config/NinMagicMods/update-url.txt` permite elegir otro manifiesto HTTPS válido. Sin ese archivo se usa el canal integrado. Si la publicación coincide con el programa y el NRO instalado, la pantalla muestra No hay actualizaciones pendientes. Un error de red mantiene la consulta sin comprobar.

## Compilación y validación

Con devkitPro, devkitA64, libnx, zlib, libcurl y switch-tools en Windows:

```powershell
.\tools\build.ps1 -ExpectedVersion 1.0.0 -Preview
```

La compilación usa una carpeta temporal dedicada bajo el perfil del usuario y no escribe en la consola. Las pruebas utilizan servicios simulados, archivos públicos de referencia o carpetas temporales del PC. Se comprueban metadatos, identidad de juego, compatibilidad de fuentes, conversión de parches, conflictos, copias, recuperación, actualizador y pantallas. Compilar y superar esas pruebas no sustituye una prueba en una consola real.

Logo de NinMagic adaptado por petición de su propietario usando la herramienta de imágenes integrada. Emblema conservado con MODS en neón magenta y violeta; especificación y origen en `docs/logo-generation.json`. Avisos de libnx, zlib, curl y DejaVu Sans incluidos.
