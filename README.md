# Furgoneta Solidaria

## Introducción

Proyecto que implementa la web para froita.com. Ha sido realizada
mediate [Jekyll](https://jekyllrb.com/), una herramienta desarrollada en lenguaje Ruby, que
permite crear de forma bastante sencilla y potente webs estáticas. Este tipo de páginas basadas en Jekyll son muy cómodas si nuestra web la queremos alojar en GitHub, pues reconoce los proyectos realizados con esta herramienta y nos facilita su publicación y desarrollo.

Ruby es un leguaje de programación interpretado, similar a un Python o PHP. Los distintos módulos desarrollados por los programadores se denominan gemas. Existe una web donde podemos descargar gemas denominado [RubyGems](https://rubygems.org/). Aquí es desde donde podemos descargar Jekyll.

Jekyll permite que desarrolladores implementen plantillas de web y las empaqueten como una gema de Ruby, que podremos descargar y modificar según nos interese. Es una forma cómoda de afrontar un desarrollo de una web sin tener que comenzar desde cero con Jekyll. En nuestro caso vamos a usar la gema [minimal-mistakes-jekyll](https://mmistakes.github.io/minimal-mistakes/) creada por
[Michael Rose](https://github.com/mmistakes).

## Instalación del entorno de desarrollo en Windows

Para poder desarrollar nuestra web basada en Jekyll en windows necesitamos instalar una versión de Ruby específica para este sistema operativo. En nuestro caso vamos a instalar la versión 2.7 que podemos encontrar en [RubyInstaller](https://rubyinstaller.org/).

El proyecto **RubyInstaller** proporciona un instalador autónomo basado en Windows que incluye un entorno de ejecución en lenguaje Ruby y un conjunto básico de RubyGems y extensiones necesarias, integrado con una instalación de [MSYS2](https://www.msys2.org/).

**MSYS2** es una colección de herramientas y bibliotecas que proporciona un entorno fácil de usar para crear, instalar y ejecutar software nativo de Windows.

Consiste en un terminal de línea de comandos llamado **mintty**, bash, sistemas de control de versiones como git y subversion, herramientas como tar y awk e incluso sistemas de compilación como autotools, todos basados ​​en una versión modificada de [Cygwin](https://www.cygwin.com/). A pesar de que algunas de estas partes centrales se basan en Cygwin, el objetivo principal de MSYS2 es proporcionar un entorno de compilación para el software nativo de Windows y las partes que utilizan Cygwin se mantienen al mínimo. MSYS2 proporciona compilaciones nativas actualizadas para GCC, mingw-w64, CPython, CMake, Meson, OpenSSL, FFmpeg, Rust, **Ruby**, solo por nombrar algunos.

Una vez hemos instalado Ruby en nuestro sistema operativo, abrimos un terminal de windows, **cmd.exe**, y nos disponemos a instalar las dos primeras gemas necesarias para desarrollar con Jekyll. Esto se consigue con la herramienta **gem**, contenida en la instalación previa de RubyInstaller. Estas gemas con **jekyll** y **bundler**. Para instalarlas ejecutamos:

**gem install jekyll bundler**

Estas gemas quedarán instaladas dentro del directorio de instalación que hayamos elegido, en nuestro caso la ubicación es:

**C:\bin\ruby\ruby27-x64\lib\ruby\gems\2.7.0\gems**

Para verificar que Jekyll está disponible, basta ejecutarlo por línea de comandos como cualquier aplicación que se encuentre disponible en nuestro entorno, y consultar la versión:

**jekyll -v**

## Guía de Jekyll

Con Jekyll vamos a poder hacer un sitio web desde cero, aunque siempre es más sencillo partir de una plantilla de un sitio web que sea configurable y adaptarla a nuestras necesidades. Nos decantemos por una u otra la estructura báscia de carpetas siempre será la misma.

Suponiendo que nuestro directorio de proyecto es **c:\src\furgonetasolidaria.org**, dentro vamos a tener los siguientes subdirectorios y ficheros básicos:

- **Gemfile**: se trata del fichero de configuración de gemas del lenguje Ruby. En nuestra web vamos a inclir la gema de una plantilla para Jekyll, denominada minimal-mistakes-jekyll, y otras gemas que necesitamos para poder trabajar con dicha plantilla. El contenido lo podemos ver en esta web.
- **_includes**: se trata de una carpeta donde ubicar todo aquel código fuente que se repite a lo largdo del sitio o para mejorar la legibilidad del proyecto. Por ejemplo, si queremos tener un pie de página homogéneo en nuestro sitio podemos crear un fichero footer.html donde definirlo y ubicarlo en este directorio. Posteriormente mediante el tag include podremos inscrustarlo en una página web

```html
        <body>

        ...

        {% include footer.html %}


        </body>...
```

- **_data**: ficheros YAML, JSON y CSV.
- **_posts**: blog
- **_sass**:
- collections
- **assets**: directorio para guardar imágenes, código Javascript y CSS.



## Instalar GEMAS de Ruby

Crear un fichero denominado **Gemfile:** con el siguiente contenido:

```bash
source 'https://rubygems.org'
gem 'nokogiri'
gem 'rack', '~> 2.0.1'
gem 'rspec'
```

Y a continuación en el directorio donde hemos creado el fichero Gemfile, utiliando una gema ya instalada denominada **bundle** ejecutamos:

```bash
bundle install
```

Gemas necesarias para que funcione la platilla minimal-mistakes-jekyll:

gem "minimal-mistakes-jekyll"

gem "tzinfo-data"

gem "wdm", "~> 0.1.0" if Gem.win_platform?

gem "jekyll-paginate"

gem "jekyll-sitemap"

gem "jekyll-gist"

gem "jekyll-feed"

gem "jemoji"

gem "jekyll-include-cache"

gem "jekyll-algolia"

gem "webrick"


En Linux para que arranque el comando jekyll hay que lanzarlo a través de bundle, por ejemplo:

bundle exec jekyll serve




