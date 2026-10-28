# Fuentes de NinMagic Mods

NinMagic consulta diez repositorios públicos. La primera copia incluye sus índices de archivos, no sus mods. El archivo de cada mod se descarga al comprobarlo o prepararlo y debe coincidir en tamaño y hash de objeto Git con el índice. La lista se puede actualizar manualmente; la caché reciente se reutiliza durante seis horas.

| Fuente | Alcance | Criterio de instalación |
| --- | --- | --- |
| [ADEMOLA200/Switch-Emulator-Mod-Database](https://github.com/ADEMOLA200/Switch-Emulator-Mod-Database) | Colección principalmente para emuladores, PCHTXT, IPS y paquetes | Parches estáticos con Title ID y Build ID completo exactos. Los paquetes y RomFS sin identidad verificable permanecen bloqueados. |
| [SwitchOptimizerMods](https://github.com/medinacristofer034-art/SwitchOptimizerMods) | Paquetes de ajustes por juego | Paquetes ZIP/RAR sin identidad interna comprobada: consulta, sin instalación automática. |
| [yuzu-mod-archive](https://github.com/yuzu-mirror/yuzu-mod-archive) | Archivo de mods orientados a Yuzu | Los paquetes se muestran para consulta, pero no se instalan por coincidencia de nombre. |
| [StevensND/switch-port-mods](https://github.com/StevensND/switch-port-mods) | Parches gráficos y de FPS | El autor indica que prueba en emuladores. Solo se admite una conversión estática verificable; no se presenta como probado en Switch. |
| [masagrator/NXGraphicsPatches](https://github.com/masagrator/NXGraphicsPatches) | Parches para hardware Switch | Build ID completo en ExeFS; RomFS requiere una versión explícita y el Title ID correspondiente. |
| [cucholix/NX-IPS-romfs-compilation](https://github.com/cucholix/NX-IPS-romfs-compilation) | Ajustes gráficos para Switch | El autor especifica requisitos de hardware/frecuencias y pruebas en Mariko. La app no altera frecuencias. Los paquetes RAR y los datos sin identidad verificable se bloquean. |
| [StevensND/ue4-emuswitch-60fps](https://github.com/StevensND/ue4-emuswitch-60fps) | Parches de FPS y gráficos de Unreal Engine | Mismas comprobaciones de identidad y formato estático. Los archivos comprimidos no se instalan. |
| [Kenji-NX/switch-pchtxt-mods](https://github.com/Kenji-NX/switch-pchtxt-mods) | PCHTXT por Title ID y versión | Se compara el Build ID declarado dentro del archivo y la versión cuando está declarada. |
| [theboy181/switch-ptchtxt-mods](https://github.com/theboy181/switch-ptchtxt-mods) | Parches y paquetes históricos | Los paquetes sin identidad interna verificable permanecen bloqueados. |
| [h2y/BOTW-Chinese-Linkle](https://github.com/h2y/BOTW-Chinese-Linkle) | Diálogos chinos complementarios para Linkle en BOTW | Proyecto informativo. No incluye el modelo del personaje. Requiere un 7z y no declara una versión de juego verificable, por lo que no se instala automáticamente. |

[GitHub Topics: switch-mods](https://github.com/topics/switch-mods), facilitado por el usuario, se utiliza para descubrir proyectos. Es un directorio, no una base de descargas con metadatos de compatibilidad. No se hace pasar una página de temas por un proveedor que pueda instalar mods.

## Compatibilidad

Un juego se reconoce por su Title ID. Los parches ExeFS requieren el Build ID NSO completo leído de su ejecutable efectivo. Un identificador más corto solo puede completarse con ceros finales conforme al formato del autor y debe coincidir con los 32 bytes del ejecutable; nunca se compara únicamente un prefijo. Si la versión declarada también está presente, debe coincidir exactamente.

Un nombre similar permite mostrar un resultado para consultar, pero no autoriza a instalarlo. En PCHTXT, un Title ID explícito dentro del archivo puede acreditar su identidad. Los mods RomFS no contienen un Build ID de ejecutable por sí mismos: se exige una versión explícita, Title ID exacto y una fuente que documente hardware Switch. No se interpreta «Any», «latest» ni una versión ausente como compatibilidad.

Las categorías de FPS, gráficos, ropa y personajes sirven para ordenar los resultados. Tener una categoría no demuestra que un archivo sea compatible. La ropa y los personajes de fuentes externas suelen requerir paquetes, dependencias o instrucciones que no aportan metadatos verificables; estos resultados permanecen bloqueados. No se inventan modelos, versiones o códigos.

La instantánea 1.0.0 tiene 3.420 opciones de diez fuentes, con 76 grupos RomFS. Incluye cinco archivos PCHTXT de «Zelda Hood Down» (Echoes of Wisdom: versiones 1.0.1, 1.0.2 y 1.1.0, algunas repetidas entre recopiladores) bajo Ropa. Son un ajuste de vestimenta, no modelos externos nuevos. El resultado de Linkle es únicamente la información del complemento de diálogos y permanece bloqueado. No se anuncia como un modelo de personaje instalable.

En esa instantánea sólo tres grupos RomFS de la fuente física de masagrator aportan Title ID y versión explícita mediante rutas inequívocas: Garfield Kart Furious Racing 1.0.1, Overcooked 2 1.0.9 y Thronebreaker 1.0.1. Los otros grupos no se habilitan usando una versión supuesta. Una actualización del catálogo puede cambiar ese inventario, conservando las mismas comprobaciones.

La coincidencia de identidad y el formato correcto reducen riesgos, pero no certifican el funcionamiento del mod ni evitan todos los cierres. Se conserva el enlace al autor, sus requisitos y el motivo de bloqueo. No se instalan plugins NRO, sysmodules, cheats, configuraciones de overclock ni guardados como si fueran mods RomFS.

## Créditos y redistribución

Los autores y recopiladores conservan sus derechos. Los índices incluidos contienen rutas y metadatos públicos de GitHub, no los archivos de los mods. Las descargas verificadas van directamente al caché privado de la consola desde los repositorios originales. La aplicación conserva enlaces a cada fuente. El proyecto de h2y declara CC BY-SA 4.0 y se enlaza su página; el paquete 7z no se redistribuye.

Fuentes de formato: [IPSwitch](https://github.com/3096/ipswitch), [Atmosphère](https://github.com/Atmosphere-NX/Atmosphere). La conversión conserva los bytes habilitados por el autor y rechaza instrucciones desconocidas o contradictorias.


## GameBanana desde 1.1.0

Además de los diez repositorios, se consulta GameBanana por el juego seleccionado. Se utiliza su API pública v11 y se muestra la procedencia original. Las identidades GameBanana verificadas por Title ID se combinan con una búsqueda dinámica que exige nombre exacto normalizado y plataforma Switch; un resultado parecido o ambiguo no se convierte en el juego instalado. Un fallo o identificación insuficiente se distingue de una búsqueda sin resultados.

Las consultas y la paginación tienen límites y caché privada de seis horas. GameBanana permite encontrar personajes y ropa que no figuran en las recopilaciones GitHub. Se consultó como referencia la documentación y el código de [SimpleModDownloader](https://github.com/PoloNX/SimpleModDownloader), que obtiene sus mods de GameBanana. Los otros gestores aportados por el usuario gestionan bibliotecas locales, no nuevas fuentes online.

La versión publicada de un mod, como 1.0, no es la versión del juego. Actualmente los paquetes de GameBanana se muestran para consulta y permanecen bloqueados cuando no existe una compatibilidad de juego verificable; no se extraen automáticamente por tener una carpeta romfs. No se redistribuyen sus modelos ni paquetes en el ZIP de NinMagic.

Caso comprobado: [Vegeta para Wonder](https://gamebanana.com/mods/556710), de diegoforfun, sustituye a Luigi. El paquete oficial contiene ocho archivos RomFS y no declara versión de juego ni Build ID, por lo que no se habilita para Wonder 1.2.1 como si estuviera probado.
