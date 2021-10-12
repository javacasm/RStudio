## Introducción

* ¿Qué es R?
* ¿Para qué se utiliza?

## Instalación

Seguimos las [instrucciones del sitio ofical de R](https://cran.r-project.org/bin/linux/ubuntu/#install-r)

```sh
sudo apt update -qq
# install two helper packages we need
sudo apt install --no-install-recommends software-properties-common dirmngr
# add the signing key (by Michael Rutter) for these repos
# To verify key, run gpg --show-keys /etc/apt/trusted.gpg.d/cran_ubuntu_key.asc 
# Fingerprint: 298A3A825C0D65DFD57CBB651716619E084DAB9
wget -qO- https://cloud.r-project.org/bin/linux/ubuntu/marutter_pubkey.asc | sudo tee -a /etc/apt/trusted.gpg.d/cran_ubuntu_key.asc
# add the R 4.0 repo from CRAN -- adjust 'focal' to 'groovy' or 'bionic' as needed
apt install --no-install-recommends r-base add-apt-repository "deb https://cloud.r-project.org/bin/linux/ubuntu $(lsb_release -cs)-cran40/"
```

No funciona en elementary porque lsb_release devuelve "hela"

Cambiamos en /etc/apt/sources.lst "hela" por "bionic" (su correspondiente ubuntu) 

Instalamos r-base 

```sh
sudo apt install --no-install-recommends r-base
```

En mi caso (Elementary) he tenido que instalar algunas librerías

1. Instalamos dependencias de 

```sh
sudo apt-get install libz-dev libpng-dev libjpeg-dev libcurl4 libcurl-openssl1.0-dev libcurl4-openssl-dev libblas-dev liblapack-dev

y ejecutamos como administrador para poder instalar paquetes:

```sh
sudo R 
```

Ahora instalamos paquetes desde dentro de R Para instalar los paquetes para todos los usuarios

Para usar R-commander ejecutamos desde dentro de R:

```
install.packages("Rcmdr",dependencies=TRUE)
``` 

[Detalles del tutorial de instalación de la OSL](https://osl.ugr.es/wp-content/uploads/2010/03/instalaR.pdf)


## RStudio

Es un entorno de programación comercial considerado como el estándar y que nos permite trabajar cómodamente con R. Dispone de una versión gratuita Open Source y de otras de pago con soporte y opciones 

Podemos descargarlo desde su [página de descargas](https://www.rstudio.com/products/rstudio/download/#download), tanto la versión gratuita como la Comercial Pro

También podemos elegir entre una instalación de escritorio, que consiste en la típica aplicación, y una versión RStudio Server con la que trabajaremos desde el navegador.

Si descargamos la versión de escritorio, la instalaremos con:

```sh
sudo gdebi rstudio-2021.09.0-351-amd64.deb
```

**gdebi** es un instalador que nos va a permitir de forma sencilla instalar todas las dependencias de un paquete dado. Si no lo tenemos, podemos instalarlo con

```sh
sudo apt install gdebi
```



## Cursos/Tutoriales

[Introducción a RStudio por Pedro Angel Castillo](http://yosigopublicando.ugr.es/?s=rstudio)

[Curso de R para principiantes](https://plataforma.keepcoding.io/courses/1464950/lectures/33577020)

