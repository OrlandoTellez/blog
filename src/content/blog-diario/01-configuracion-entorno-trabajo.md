---
titulo: Configuración de entorno de trabajo
fecha: 20/12/2025
dia: día 1
descripcionPrevia: Configurando Lazyvim para ser más productivo a la hora de programar
layout: "../../layouts/PlantillaArticulos.astro"
---

# Configurando LazyVim - Día 1

#### Fecha: 20 de diciembre del 2025

Hola, mi nombre es Orlando Tellez y este es mi primer artículo de mi blog, hay 2 reglas claras que tengo que cumplir para cada uno de mis artículos de ahora en adelante:
1. No usar inteligencia artificial para redactar cada artículo.
2. Escribir todo lo que haga o aprenda en el día con respecto a la programación.

Quiero dejarlo todo claro, mi intención es documentar mi aprendizaje, siento que es beneficioso para recopilar lo aprendido en el día, estoy seguro que hay estudios al respecto, solo que no los he leído xd.

## ¿Por qué Neovim?
Estoy adentrandome en el mundo de Neovim como editor de código para mejorar la productividad, hace unos meses me pasé a Debian 13 usando de interfaz gráfica Gnome, me gusta mucho la estética, es simple y minimalista, me gusta poder alternar rápidamente entre mis escritorios y trabajar más ordenado.

El punto es que empecé como siempre con Visual Studio Code, ya estaba muy acostumbrado a usarlo, desde hace unos 3 años que lo uso, ahora bien, ¿Por qué decidí cambiarme a Neovim? pues la verdad solo me bastó ver algunos videos de personas usándolo para querer implementarlo en mi día a día, me sorprendía bastante el manejo de comandos que tienen estas personas, realmente creo que entre menos uso el mouse tengo una mejor experiencia de desarrollo, claro siempre y cuando de eso se traté, cosas como diseño pues obviamente el mouse es obligatorio.

## Curiosidad
Ya tenía una configuración de neovim, sin embargo el día de ayer estuve borrando varias cosas de mi sistema y pues por accidente borré el archivo de configuración que tenía de neovim, lo peor de todo es que no tenía mi configuración en github, así que se perdió por completo. Sin embargo hoy empecé desde 0, de hecho está mucho mejor de como lo tenía antes, le agregué un mejor tema y estuve aprendiendo más comandos para manejarme entre la estructura de archivos y el código.

## Configuración de neovim
Mi configuración de neovim ya la tengo en mi repositorio, está en privado, aún no tengo planes de ponerlo público, hasta que me adapte mejor y le agregue más cosas, para mientras estaré acostumbrandome más. Haré más adelante guías más técnicas de este tipo de configuraciones, por el momento sencillamente hice lo siguiente para la instalación de LazyVim paso a paso:

## Paso 1:

Ejecutar el siguiente comando en la terminal para descargar desde el repositorio oficial de github de neovim, en este caso la versión más reciente

    cd /tmp
    curl -LO https://github.com/neovim/neovim/releases/latest/download/nvim-linux-x86_64.tar.gz

## Paso 2:

Extraerlo en /opt, esto se hace en la misma carpeta /tmp

    sudo tar -C /opt -xzf nvim-linux-x86_64.tar.gz

Para verificar la instalación podemos ir a revisar la carpeta /opt

    ls /opt/nvim-linux-x86_64

Verificamos igual la versión

    nvim --version

## Instalación de lazy vim:
En caso de ser necesario eliminar caché vieja de anteriores intalaciones:

    mv ~/.config/nvim ~/.config/nvim.bak 2>/dev/null
    mv ~/.local/share/nvim ~/.local/share/nvim.bak 2>/dev/null
    mv ~/.cache/nvim ~/.cache/nvim.bak 2>/dev/null

Ahora si instalar lazy vim del repositorio oficial:

    git clone https://github.com/LazyVim/starter ~/.config/nvim

Eliminar .git de la plantilla:

    rm -rf ~/.config/nvim/.git



## Estableciendo algunos conceptos
Aún no me he explicado mejor de acerca de lo que es Neovim y Lazyvim, estuve viendo algunos videos y leyendo un poco, no soy tan experto en el tema, pero puedo decir que Neovim es básicamente un fork de Vim(se usa para editar texto en la terminal en linux, otra alternativa que no me gusta es nano), claramente empecé con nano porque es más rápido y directo, o al menos así lo siento yo, porque no hay necesidad de aprender tantos comandos(ni tan complicados son pero amerita aprendérselos).

Vim es muy simple, Neovim agrega mejoras es Vim, como poder ver la estructura de carpetas, poder navegar, una mejor experiencia, pero aún le hace falta algo, y es que no se siente como un editor completo, y de ahí surge Lazyvim, es una mejora de configuración de Neovim, me gusta verlo como los frameworks de JavaScript que dan una estructura inicial para empezar a trabajar, pues Lazyvim da una estructura inicial y con muchas más funcionalidades de personalización y edición que Neovim. Me está gustanto mucho sin embargo aún me hace falta mucho para ser lo realmente productivo que es posible llegar a ser con esta herramiento, borré por completo Visual Studio Code, así que ya veremos que tal me va.

## Plugins
instalé algunos plugins con los que he trabajado sin ningun problema con JavaScript, TypeScript y Rust:
    astro-language-server 
    css-lsp 
    emmet-ls emmet_ls
    eslint_d
    lua-language-server lua_ls
    prettierd
    rust-analyzer 
    shfmt
    stylua
    tree-sitter-cli
    tsp-server 
    typescript-language-server 
  
Cada uno de esos plugins los instalé con Mason, es practicamente un administrador de paquetes que tiene LazyVim, ahí puedo instalar dependencias, plugins, LSP, etc

Habalndo de LSP(Lenguage Server Protocol), este es un protocolo que tiene un propósito, y es el de dar contexto del lenguaje en el que estamos programando en el editor de codigo, haciendo posible que el editor entiendo el lenguaje, la sintaxis, los errores, las inferencias, las importaciones, todo acerca del lenguaje en el que estamos trabajando, si no se instalan LSP es como escribir código como un maniático sin autocompletando, inferencia y sin ver los errores o sugerencias.

## Con respecto al blog
Aún no he terminado el diseño del blog, ante la idea era hacer tutoriales de JavaScript pero la verdad lo dejé de lado, me gusta más la idea de documentar lo que hago, que cosas aprendo o los proyectos en los que trabajo. Así que el blog será orientado a eso y también a hacer artículos más técnicos de las aplicaciones y del desarrollo de mis proyectos, en el apartado de Blog diario es nada más un resumen de lo que trabajé en el día.














