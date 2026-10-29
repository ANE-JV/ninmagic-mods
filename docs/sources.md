# Fuentes de NinMagic Mods 1.4.1

La aplicación consulta los índices de estos repositorios y descarga archivos desde sus revisiones originales, comprobando tamaño y hash Git:

| Fuente | Contenido |
| --- | --- |
| [masagrator/NXGraphicsPatches](https://github.com/masagrator/NXGraphicsPatches) | Parches de gráficos y FPS, y recursos RomFS. |
| [cucholix/NX-IPS-romfs-compilation](https://github.com/cucholix/NX-IPS-romfs-compilation) | IPS, PCHTXT y paquetes de recursos; se conservan requisitos del autor de Mariko y frecuencias. NinMagic no aplica overclock. |
| [h2y/BOTW-Chinese-Linkle](https://github.com/h2y/BOTW-Chinese-Linkle) | Recursos e instrucciones complementarias de Linkle. Los 7z u otros formatos no admitidos no se convierten automáticamente. |

[GameBanana](https://gamebanana.com/) se consulta por juego: se conservan autor, enlace, identificador del juego/mod/archivo y descripción. Hasta 90 publicaciones por juego en el NRO y 45 en el overlay, además de referencias destacadas. No es una copia completa de su catálogo histórico. La caché reciente se reutiliza durante seis horas.

## Selección e instalación

El usuario elige qué instalar sin un paso separado de revisión de compatibilidad. La ausencia de versión o evidencia de hardware no bloquea los formatos admitidos. Tampoco se interpreta esa ausencia como compatibilidad comprobada. La versión del mod y la versión del juego se muestran por separado.

Los parches conservan el Build ID que declara el autor. No se cambian a otro Build ID para forzarlos sobre el ejecutable instalado. Para convertir PCHTXT o instalar IPS sigue siendo necesario que el archivo contenga un destino de parche válido. RomFS usa las rutas del juego seleccionado; un Title ID interno contradictorio se rechaza.

Se mantiene la exclusión de entradas declaradas expresamente exclusivas de emuladores y la comprobación de fuente, rutas, hashes y archivos corruptos. Un archivo que indica «no probado» no se considera automáticamente incompatible. Las recopilaciones exclusivas de emuladores no se añaden como fuentes.

Las publicaciones identificadas como herramientas o generadores para PC se excluyen del listado de mods instalables. El filtro usa los datos publicados por el autor y también se aplica al leer la caché. Los mods preparados para Switch no se descartan por el mero hecho de que su documentación mencione un PC. Si el contenido real del archivo revela un programa de PC que no estaba identificado en sus metadatos, se muestra el motivo y no se instala.

Los ZIP/RAR se procesan automáticamente al preparar los mods elegidos. GameBanana puede ofrecer varios archivos: se elige una variante concreta; un ZIP con variantes ambiguas no se descomprime a ciegas sobre la SD. Se conservan los límites de 128 MiB por paquete, las comprobaciones de checksum y los destinos HTTPS permitidos.

La aplicación identifica el contenido instalado antes y durante la operación para evitar escribir sobre otro juego o una selección que cambió. Esta comprobación de destino no certifica la compatibilidad del mod. Los datos informativos de versión y Build ID del juego pueden estar ausentes.

## Retirada y derechos

Los archivos originales se guardan antes de reemplazarlos. **L → Retirar** restaura esos archivos y quita los que NinMagic añadió; requiere el juego cerrado. Los recibos conservan hashes y rutas para detectar modificaciones externas. Desde 1.4.1 también registran la identidad y el nombre de los mods de una instalación completada para mantener sus casillas marcadas. Los recibos antiguos siguen sirviendo para retirar, aunque no permiten identificar cada nombre. No se borran partidas ni se revierten cambios guardados en ellas.

Los autores y recopiladores conservan sus derechos. Las descargas van directamente a la consola desde los servidores originales. El paquete de la aplicación incluye índices públicos y su propio código, no los mods de terceros. El proyecto h2y declara CC BY-SA 4.0; consulta su publicación y las condiciones de cada autor.

Fuentes de formato: [IPSwitch](https://github.com/3096/ipswitch) y [Atmosphère](https://github.com/Atmosphere-NX/Atmosphere). Se conservan las instrucciones habilitadas del autor y se rechazan instrucciones desconocidas o contradictorias.
