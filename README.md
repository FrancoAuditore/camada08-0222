# Clase 13s

## Diseño Adaptativo

A lo largo de esta clase vimos conceptos como 

- **Medias Relativas** ( porcentajes, viewport height and width, rems, ems )
- **Etiqueta meta**  configuramos el sitio tanto para el viewport como para otras propiedades
- **Concepto de breakpoints y media queries** aplicada a distintos media types

## Resumen de algunos conceptos 
*IMPORTANTE: En los ejemplos de código observaremos el estilo definido en linea directamente en la propiedad style, recuerden que esto NO DEBE HACERSE*

### Medidas Relativas
Las medidas relativas son  aquellas que se ven modificadas de acuerdo al contexto. Es decir si su contexto cambia estas pueden cambiar 

### Porcentajes:
Es la mas comun. Esta depende de su padre. Es decir que el porcentaje esta sujeto al de su padre.
**Por ejemplo**

```
  <div style="width: 600px;">
    <div id="elemento" style="width: 50%;"></div>
  </div>

```
Elemento tendrá un 50% de ancho en relación a su padre. Es decir medira 300px ya que el 100% es de 600px

### Unidades de Medida en relación al viewport: vw / vh

En este caso la referencia no es el tamaño del padre si no el tamaño del viewport donde:

  - **30vw** =>  30% en relacion al ancho del viewport
  - **40vh** =>  40% de alto en relacion al viewport

### Medidas Relativas EM / REM

Estas medias estan relecionadas al trabajo con tipografias. 
  
### Medidas EM: donde su medida es relativa a su padre

**Por ejemplo:**

El tamaño inicial, *salvo que se defina lo contrario*, de los textos es de **16px** por lo tanto 
```
  1em    => 16px
  1.5em  => 24px (16px * 1.5)

```

*IMPORTANTE: Los ems siempre se calculan en relación al valor de su padre*

```
  <body>
      <div class="seccion" style="font-size: 1em">
        <span>Hola Mundo </span> <br>
        <span style="font-size: 2em">Bienvenidos</span>
      </div>
  </body>

```
**El tamaño del textos 'Bienvenidos' es => 32px**

### Medidas REM (recomendado)

Los rems son el valor recomedado para trabajar y funcionan similar a los ems con la diferencia de que el valor de referencia es siempre la base del tamaño del HTML (font-size)

Por lo tanto los elementos hijos NO SE VERAN afectados por el valor del tamaño de fuente de los elementos
padre

```
  <body>
      <div class="seccion" style="font-size: 3rem">
        <span>Hola Mundo </span> <br>
        <span style="font-size: 3rem">Bienvenidos</span>
      </div>
  </body>

```

**El tamaño del textos 'Bienvenidos' y 'Hola Mundo' es => 48px**

Porque toma como referencia el valor raíz de 16px


### Etiqueta meta

El proposito es incluir información en el sitio web como también configuraciones, es una etiqueta
multipropósito que me permite dar los datos del *autor, palabras claves,etc*

**Ejemplos de implementaciones**

```
<meta charset="UTF-8">
<meta name="Author" content="Renzo Vinci">
<meta name="keywords" content="Clase 13, Diseño adaptativo, HTML">
<meta name="audience" content="all">
<meta name="category" content="elearning ctd">
<meta name="description" content="Este es el sitio web de la clase 13">
<meta name="copyright" content="Digital House">
<meta name="viewport" content="width=device-width, initial-scale=1">
<meta name="robots" content=index, nofollow"> 

```
### Atributos genéricos

-**Lang** => Atributo que proporciona información sobre el idioma del contenido del elemento

### Atributos específicos

- **name**        => metainformación a asignar (*author, description, keywords, copyright, etc*)
- **charset**     => codificación del charset
- **content**     => los datos que se asocian al valor name
- **http-equiv**  
- **schemel** 

### Información para crawlers (arañas)

**robots** => Hace referencia a los crawlers (arañas) de los motores de busqueda que informacion debe y que información no debe ser tomada en cuenta para la indexación 

index     => permite la indexacion de una pagina
noindex   => prohibe al buscador transferir contenido de una pagina HTML a su base de datos ( no la muestra en resultados de busqueda)

follow    => le indica al crawler que siga los enlaces de la pagina
nofollow  => impide que rastree los enlaces de esta

**Ejemplos:**

```
<meta name="robots" content="index, nofollow" />
<meta name="robots" content="index, follow" />
<meta name="robots" content="noindex, nofollow" />

```
### Viewport

Indica al navegador que no importa el dispositivo donde se este visualizando que el documento debe 
ocupar el 100% del ancho del dispositivo

```
<meta name="viewport" content="width=device-width, initial-scale=1">

```

- **device-width**   =>  es el ancho del dispositivo
- **initial-scale**  =>  establece el zoom inicial de la pagina
- **minimun-scale y maximun-scale**  =>  establece el minimo y maximo zoom 
- **user-scalable**  => Define si el usuario podra o no hacer zoom en la pagina (en mobile con dos dedos)
