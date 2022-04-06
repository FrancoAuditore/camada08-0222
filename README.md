# Clase 16s pseudoselectores

- Selectores que se aplican sobre un selector existente para modificar un comportamiento determinado o el comportamiento del HTML
- Se dividen en dos grupos

## Pseudo clases
  Se aplican sobre un selector seguido de :. Existen pseudoclases generales y otras especificas para ciertos elementos 


  - :link     => Elementos no visitados en el navegador
  - :visited  => Elementos o enlaces ya visitados
  - :hover    => Cuando paso el mouse sobre el selector que tiene aplicado hover
  - :active   => Cuando le doy click al elemento
  - :target   => Cuando el elemento ha sido marcado
  - :focus    => Cuando hago foco en el elemento
  - :checked  => Cuando esta seleccionado un check
  - :focus-within  => elemento que tenga un hijo en estado focus
  - :not      => Niego alguna condicion 

  ```
    h3:not(.title){}

  ```

  ```
    input[type="checkbox"]:checked + label {}

  ```
  - only-of-type    => unicos en su seccion o en su padre. No debe tener hermanos de su mismo tipo
  - first-of-type   => primer elemento de su tipo dentro del contenedor o padre
  - last-of-type    => ultimo elemento de su tipo dentro del contenedor
  - nth-of-type(n)  => selecciona los elementos en la posicion definida por N de su mismo tipo en el contenedor o padre. (odd => impares / even => pares)
  - nth-last-of-type() => inverso al anterior

  ## Childs: debe cumplirse la condicion para que funcione el selector

  - only-child{}    => siempre que sea hijo unico sin considerar el tipo
  - first-child{}   => primer hijo del contenedor, si no es el primero no se selecciona (debe estar en la primer posicion)
  - last-child{}    => inverso al anterior
  - nth-child(n)    => seleccion el hijo de acuerdo a la condicion de n
  - nth-last-child(n)


## Pseudo elementos
  Manipulan el contenido de un elemento presente en el HTML. Añaden un estilo a una parte concreta de los elementos

  - ::first-letter
  - ::selection
  - ::first-line
  - ::after
  - ::before 
