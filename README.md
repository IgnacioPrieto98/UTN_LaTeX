# UTN-FRRq - TALLER DE LATEX 

Este repositorio posee como objetivo:

- Ofrecer diferentes ejemplos que permitan solucionar dudas generales y puntuales.
- Facilitar el manejo de documentos realizados por los integrantes del taller de LaTeX.
- Ofrecer diferentes plantillas para desarrollos académicos como: proyectos finales, trabajos prácticos, monografías, etc.

## Estructura de los documentos referidos a cátedras de UTN - FRRq

La intensión de los documentos a realizar es informar sobre los contenidos presentes en la cátedra. Por esta razón se propone el trabajo a partir de los *legajos de cátedra* de cada una de ellas. 

La estructura a seguir será:

- Cada **UNIDAD** de la cátedra representará un **CAPÍTULO**.
- Cada **ELEMENTO DENTRO DE LA UNIDAD** de la cátedra representará un **SECCIÓN**.

En ciertas ocasiones extraordinarias, cuales se presenten debido a una dificultad en la interpretación del legajo de cátedra, se procederá a dialogar con el docente a cargo. En caso de esto no ser posible, o no presentar una solución, se definirá algún título representativo de la unidad o la sección, con el objetivo de continuar con el procedimiento.

Se debe tener en cuenta que los documentos a realizar tienen el objetivo de estar avalados por el jefe de cátedra. Por esta razón resulta fundamental poseer una retroalimentación del mismo siempre que sea posible.

## Uso de 00-PLANTILLA-V1.0

El uso de esta plantilla permite, mediante muchas simplificaciones de código, realizar un documento de alta calidad tipográfica con un básico entendimiento de LaTeX. 

### Configuración previa en TeX-Studio

Como medida fundamental para el uso de la plantilla se debe tener en cuenta que la misma debe ser compilada en *XeLaTeX*, debido al uso de fuente *montserrat*. Para onfigurar esto se realiza la siguiente secuencia de pasos dentro de *TeX-Studio*:

- Se ingresa a *Opciones* en la barra de herramientas de *TeX-Studio*.
- Hecho esto, se selecciona 🔧*Configurar TeX-Studio*. 
- Dentro de la ventana emergente 🔧configurar TeX-Studio, sobre la barra izquierda, se ingresa a *compilar*.
- Seleccionado compilar, se altera la opción *Compilador por defecto* cambiando la misma a: *XeLaTeX*.

### Estructura de los archivos en la plantilla

La carpeta *00-PLANTILLA-V1.0* presente en el repositorio posee los siguientes elementos:

- Base.tex

Archivo de .TeX cual vincula el estilo del documento y las diferentes unidades que estarán añadidas al mismo.
  
- STY-UTN-LTX-CATEDRAS.sty

Archivo .Sty cual posee las configuraciones generales del estilo del documento.

- Capitulos (carpeta de archivos).

Carpeta la cual contiene los archivos .TeX referidos a cada una de las unidades.

- ElementosBase (carpeta de archivos).

Carpeta la cual contiene archivos .png (imagenes) cuales conforman la estética del documento, y un archivo .TeX el cual representa la configuración de la primer página del documento.

### Uso de plantilla

El uso de la plantilla consta de una configuración de datos, cual se realiza una única vez por documento al comienzo o al final; y un desarrollo de contenido. Para realizar la configuración de datos, se procede a ingresar a *Base.TeX* y configurar:

``` TeX
%---PARÁMETROS PARA DEFINIR---%
\def\supervisor{-Supervisor-}
\def\titulo{-Título del documento-}
\def\subtitulo{-Subtítulo del documento-}
\def\autor{
	-Autor de documento 1-\\
	-Autor de documento 2-
	}
```

Una vez configurados estos parámetros, se procede realizar un archivo .TeX por unidad de la cátedra, y guardarlo en la carpeta de unidades y comenzar a trabajar en ellas. Para que estas unidades sean tomadas en el documento base se procede a utilizar el comando \include{-ruta de la unidad-} dentro del entorno *document* del archivo *Base.TeX*, como se muestra a continuación:

``` TeX
\begin{document}
	
	\include{ElementosBase/PaginaTitulo.tex}
		
	\tableofcontents

	\pagestyle{HojaContenido}
	
	%Inclusión de unidadaes
	\include{Unidades/UN1-TITULO DE LA UNIDAD} %Inclusión de la unidad 1
	\include{Unidades/UN2-TITULO DE LA UNIDAD} %Inclusión de la unidad 2
	\include{Unidades/UN3-TITULO DE LA UNIDAD} %Inclusión de la unidad 3
	
\end{document}

```

Creados y añadidos los archivos de las unidades, se comienza a trabajar en ellas. Para realizar esto se procede a desarrollar el contenido mediante texto e imagenes con las siguientes salvedades:

- Previo a la definición del capítulo, se debe presentar el comando \Res{-Resumen-}, el cual permite incluir un resumen de cada capítulo/unidad.
- Previo a la definición de la sección, se debe presentar el comando \Bib{-Resumen-}, el cual permite incluir una bibliografía recomendada de la sección.

A continuación se presenta un ejemplo del código con dichas salvedades:

``` TeX
\Res{-Resumen del capítulo-}	
\chapter{Título de capítulo}

\Bib{-Bibliografía recomendada de la sección-}
\section{Título de la sección}
```
