# EventosJS
## Ejemplo de eventos en JS

### ¿Qué es un evento en JS?

>
> En evento es un indicativo o señal de que algo ha ocurrido. Todos los nodos del DOM generan esta señales.
> 
>>**DOM** es la abreviatura de **D**ocument **O**bject **M**odel
>> 
>> El **DOM** es la estructura de objetos que genera el navegador cuando se carga un documento y se puede alterar mediante Javascript
>> para cambiar dinámicamente los contenidos y aspecto de la página.
>
 
   - #### Lista de eventos más representativos del DOM

      - #### Eventos de mouse 🖱️

            click                - cuando se hace click con el mouse o se hace touch sobre un elemento.
            contextmenu          - cuando se hace click derecho con el mouse sobre un elemento.
            mouseover / mouseout - cuando el puntero del mouse ingresa / abandona un elemento.
            mousedown / mouseup  - cuando el botón del mouse es presionado / soltado sobre un elemento.
            mousemove            - cuando el mouse se mueve.

      - #### Eventos de teclado ⌨️
            keydown / keyup  - al presionar / soltar una tecla.

      - #### Eventos de elemento form ⏏️
            submit - cuando el usaurio envía un <form>.
            focus  - cuando el usuario se centra sobre un elemento.

      - #### Eventos de documento 📋
            DOMContentLoaded - cuando el HTML es cargado y procesado, el DOM está completamente construido.

      - #### Eventos de CSS :
            transitionend - cuando una animación CSS concluye.


- ### preventDefault
      Previene que la acción por defecto asociada o las funciones incorporados en el elemento del DOM se
      ejecuten.
      Es una función dentro dentro de un objeto y no funciona sin su evento.
      
- ### stopPropagation
      Evita que se realize la propagación de los eventos/funciones hacia los ancentros del elemento,en 
      otras palabras, se detiene el efecto burbuja, pero todos los eventos/funciones en el elemento actual
      se ejecutarán.
      
- ### Propagación de eventos
  **Principio de Propagación**
      
      Cuando un evento ocurre en un elemento, este primero ejecuta los eventos/funciones que tiene asignados,
      luego los eventos/funciones del padre, y así hasta otros ancestros.
      
     <img src="/images/propagacion.png" alt="Ejemplo Propagación Eventos" style="height: 200px; width:410px;"/>
 
      Así si hacemos click en <p>, entonces, veremos 3 eventos: p → div → form.

      Este proceso se conoce como “propagación” porque los eventos “se propagan” desde el elemento más al
      interior a través de los padres, como una burbuja en el agua.
      
- ### Fases de los eventos
 1. Fase de Captura
    Cuando el evento desciende hasta llegar al elemento
 2. Fase de Objetivo
    Cuando el evento alcanza al elemento.
 3. Fase de Propagación
    Cuando el evento se propaga de elemento hacia arriba como un efecto burbuja.
 
    Sí definimos un evento en el elemento <td> entonces las diversas fases se pueden explicar de la siguiente manera:
    
         <html>
          <body>
           <table>
            <tr>
             <td>
              
       **Fase de Captura** - el evento pasa a través de los ancestros que son **HTML, BODY, TABLE, TR** hasta alcanzar el elemento **_TD_**.
              
       **Fase de Objetivo/Target** - una vez alcanzado el elemento, el evento de ejecuta o desencadena.
              
       **Fase de Propagación** - cuando se regresa hacia los ancestros y va ejecutando los eventos que se encuentre en el camino ya que ahora
                                 la ruta será **_TD_**, **TR, TABLE, BODY, HTML**.
 
 ### Event Emitter y eventos en NodeJS
    Todos los objetos que emiten eventos son instancias de events.EventEmmiter y permite escuchar "eventos" y asignar acciones
    para ejecutar cuando se producen esos eventos, y aquí podemos emitir eventos por nuestra cuenta, cuando se quiera y no en 
    función de la interacción con el usuario, y se basan el principio llamado "modelo de publicación/suscripción", porque 
    podemos suscribirnos a eventos y luego publicarlos.
              
              
## Reto: Propagación de eventos
Resolver el siguiente reto [Propagación de Eventos](https://codepen.io/driverinside/pen/MWmOOee).

   <img src="/images/reto1.png" alt="Ejemplo Propagación Eventos" style="height: 460px; width:1000px;"/>              
   <img src="/images/reto2.png" alt="Ejemplo Propagación Eventos" style="height: 460px; width:1000px;"/>
Evitar la propagación de eventos, ya que se define un evento en el elemento **button** y en el elemento **div**.
              
**Solución:**
              
       Se coloca el evento stopPropagation en el elemento más interno que en este caso es button y con ello evitar la
       propagación o efecto burbuja hacia el elemento div.

   
   <img src="/images/reto3.png" alt="Ejemplo Propagación Eventos" style="height: 460px; width:1000px;"/>
              
 
