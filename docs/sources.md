# Fuentes de NinMagic Mods

Desde 1.2.1 NinMagic consulta tres repositorios que documentan Nintendo Switch física. La primera copia incluye sus índices de archivos, no sus mods. El archivo de cada mod se descarga al comprobarlo o prepararlo y debe coincidir en tamaño y hash de objeto Git con el índice. La lista se puede actualizar manualmente; la caché reciente se reutiliza durante seis horas.

| Fuente | Destino documentado | Criterio de instalación |
| --- | --- | --- |
| [masagrator/NXGraphicsPatches](https://github.com/masagrator/NXGraphicsPatches) | Hardware Switch | ExeFS exige Build ID completo; RomFS exige Title ID, versión explícita e identidad del contenido. |
| [cucholix/NX-IPS-romfs-compilation](https://github.com/cucholix/NX-IPS-romfs-compilation) | Switch con Atmosphère; requisitos de Mariko y frecuencias indicados por el autor | Se conservan estos requisitos. La aplicación no altera frecuencias ni instala configuraciones de overclock. |
| [h2y/BOTW-Chinese-Linkle](https://github.com/h2y/BOTW-Chinese-Linkle) | Instrucciones de Switch física para diálogos complementarios de Linkle | Actualmente no aporta formato admitido y no genera resultados instalables. Su índice no acredita un modelo ni versión de juego para instalar. |

La política exige una fuente física de la lista admitida, su rama conocida, procedencia explícita y ausencia de etiquetas exclusivas de emulador. Las recopilaciones para emuladores y de destino sin confirmar dejan de consultarse. GameBanana queda fuera porque las fichas disponibles no acreditan aquí el destino físico requerido. La misma política se comprueba al cargar cachés y selecciones anteriores, al listar y al preparar archivos.

## Compatibilidad

Un juego se reconoce por su Title ID. Los parches ExeFS requieren el Build ID NSO completo leído de los módulos del juego en ejecución, con PID verificado. Se preparan archivos para el próximo inicio, sin escribir en la memoria del juego. Un identificador más corto solo puede completarse con ceros finales conforme al formato del autor y debe coincidir con los 32 bytes del ejecutable; nunca se compara únicamente un prefijo. Si la versión declarada también está presente, debe coincidir exactamente.

Cuando el autor identifica formalmente la actualización con un Title ID terminado en 800, se relaciona con el ApplicationID del mismo juego terminado en 000 y se indica en el detalle. Esta relación de NCM no omite el Build ID ni la versión. No se interpreta un índice de programa ni un ID de DLC como si fuera el juego base; una familia distinta se rechaza.

Un nombre similar permite mostrar un resultado para consultar, pero no autoriza a instalarlo. En PCHTXT, un Title ID explícito dentro del archivo puede acreditar su identidad. Los mods RomFS no contienen direcciones de ejecutable: requieren el juego cerrado, una versión explícita, Title ID exacto y conservar los requisitos de la fuente física. La plataforma vuelve a comprobar una identidad de contenido NCM del programa y su actualización; ese registro no sustituye al Build ID de un parche ExeFS. No se interpreta «Any», «latest» ni una versión ausente como compatibilidad.

Si el autor declara expresamente un Build ID también para RomFS, se mantiene esa condición: no se permite instalar mientras esté sin verificar o sea diferente. La ausencia de un requisito de Build ID en recursos no se convierte en permiso para ignorar uno que el autor sí publicó.

Las categorías de FPS, gráficos, ropa y personajes sirven para ordenar los resultados. Tener una categoría no demuestra que un archivo sea compatible. La ropa y los personajes de fuentes externas suelen requerir paquetes, dependencias o instrucciones que no aportan metadatos verificables; estos resultados permanecen bloqueados. No se inventan modelos, versiones o códigos.

La nueva copia inicial contiene únicamente los índices de las tres fuentes físicas admitidas: 284 candidatos de formato admitido: 182 PCHTXT, 63 IPS y 39 grupos RomFS. Las 316 entradas comprimidas y la ficha informativa sin formato admitido de esas fuentes se excluyen de los resultados. El número de entradas incluye versiones diferentes, duplicados y formatos bloqueados; no representa ese número de mods instalables para cada juego. Se mantienen las categorías FPS, gráficos, ropa y personajes cuando hay archivos y metadatos que las acrediten.

En los índices revisados, tres grupos RomFS de la fuente física de masagrator aportan Title ID y versión explícita mediante rutas inequívocas: Garfield Kart Furious Racing 1.0.1, Overcooked 2 1.0.9 y Thronebreaker 1.0.1. Los otros grupos no se habilitan usando una versión supuesta. Una actualización del catálogo puede cambiar ese inventario, conservando las mismas comprobaciones.

La coincidencia de identidad y el formato correcto reducen riesgos, pero no certifican el funcionamiento del mod ni evitan todos los cierres. Se conserva el enlace al autor, sus requisitos y el motivo de bloqueo. No se instalan plugins NRO, sysmodules, cheats, configuraciones de overclock ni guardados como si fueran mods RomFS.

## Créditos y redistribución

Los autores y recopiladores conservan sus derechos. Los índices incluidos contienen rutas y metadatos públicos de GitHub, no los archivos de los mods. Las descargas verificadas van directamente al caché privado de la consola desde los repositorios originales. La aplicación conserva enlaces a cada fuente. El proyecto de h2y declara CC BY-SA 4.0 y se enlaza su página; el paquete 7z no se redistribuye.

Fuentes de formato: [IPSwitch](https://github.com/3096/ipswitch), [Atmosphère](https://github.com/Atmosphere-NX/Atmosphere). La conversión conserva los bytes habilitados por el autor y rechaza instrucciones desconocidas o contradictorias.


## Alcance de la política 1.2.1

Excluir una entrada del catálogo no desinstala archivos ya presentes en la microSD. Se conservan los recibos y las copias anteriores para que el usuario pueda retirar sus mods con el juego cerrado. No se borran partidas ni contenidos ajenos.

Los parches PCHTXT/IPS siguen requiriendo identidad completa, PID y versión coincidentes cuando corresponde. Los recursos RomFS requieren juego cerrado y las comprobaciones del contenido instalado. Una declaración de compatibilidad física por el autor no demuestra que NinMagic haya probado el efecto ni garantiza ausencia de cierres.
