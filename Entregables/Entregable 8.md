# Introducción y Contextualización del Prototipo

## Descripción breve del proyecto: Resumen del objetivo principal del prototipo.

VibroTherapy está diseñada para mejorar la experiencia del usuario en sus tratamientos y también para ayudar a la telemedicina rehabilitativa. La prenda cuenta con una placa que contiene servomotores que proporcionan vibraciones, las cuales se utilizan para señalar la zona del músculo que se está rehabilitando y el momento en que se debe hacer el ejercicio, facilitando así una terapia dirigida y efectiva. Además, incluye una app que permite al usuario monitorear su progreso, recibir mensajes del fisioterapeuta, realizar consultas y añadir notas o recordatorios personalizados. El fisioterapeuta, por su parte, puede controlar las vibraciones que se proporcionarán al paciente, dejarle recomendaciones, recibir y contestar preguntas.

## Problemática abordada: Explicación de la necesidad que motiva el prototipo.

Apoyar a personas con amputación transtibial que no pueden asistir a centros de rehabilitación, ya sea por falta de tiempo o de alguien que les ayude con el transporte, y así mismo a la telemedicina rehabilitativa con nuevos productos.

## Objetivos de la fase de integración: Breve descripción de lo que se espera lograr al integrar los componentes.

Al integrar los componentes se espera que los motores coin proporcionen una vibración al paciente la cual indique que tiene que realizar el ejercicio dado por el fisioterapeuta así como indicarle la parte del músculo que se está trabajando.

# Componentes del Prototipo

## Lista de componentes principales: Detallar cada componente y su función en el prototipo.

- ESP32: Es el microcontrolador central, controlará los motores y administra la conexión bluetooth entre la App y el sistema
- Motores Coin: Serán el mecanismo de señalización para el paciente, ya que indicarán cuando deba hacer el ejercicio y cuando parar
- Resistencias 10k Ohm. 
- AMS1117: Es el regulador de voltaje que convertirá el voltaje de entrada a un voltaje estable, para así no dañar a los circuitos
- TP4056: Este es un módulo de carga de batería LiPo. Su tarea principal es cargar de manera segura una batería LiPo, que alimentará al sistema sin necesidad de estar conectado todo el tiempo a una fuente de energía externa.
- Batería de Litio 3.7V 720mAH: Alimentará al ESP32, a los motores de vibración y otros componentes del sistema sin la necesidad de una fuente de energía externa constante
- App:  Controlará y gestionará el sistema de vibración de forma remota a través de Bluetooth, la app será la interfaz para interactuar con el sistema de terapia, proporcionando control y personalización.

## Interacción entre componentes: Explicar cómo se comunican o interactúan los distintos elementos.

- El ESP32 recibe las instrucciones de la app móvil vía Bluetooth.
- El ESP32 controla los motores de vibración según los parámetros recibidos (intensidad, frecuencia, duración).
- El TP4050 mantiene la batería LiPo cargada para garantizar que el sistema sea portátil y pueda funcionar sin estar conectado todo el tiempo.
- El AMS1117 asegura que el voltaje de la batería sea estable y adecuado para el ESP32 y otros componentes.
- La batería LiPo de 3.7V se conecta al TP4050, que se encargará de cargarla cuando sea necesario
- El AMS1117 convierte el voltaje de la batería (3.7V) a un valor estable que el ESP32 necesita para funcionar correctamente. 

## Diagrama de integración: Representación gráfica (diagrama o esquema) que muestre la disposición y conexión de los componentes.

 <p align="center">
  <img src="https://github.com/Arbandu/Fundbio/blob/8dad817a1beba9b29a5770db753f6e8b04501aed/Imagenes/diagrama%20de%20integracion.jpg" alt="Diagrama de integración">
</p>  

 # Proceso de Integración

 ## Plan de integración: Explicar el plan inicial para unir los componentes, incluyendo pasos, pruebas intermedias y objetivos específicos.

Al principio se intentó conectar los motores sin transistores ni resistencias, pero luego nos dimos cuenta que si eran necesarios ya que estos componentes son los que regulan el tiempo de encendido y apagado. Se realizaron varias pruebas, con varios tipos de resistencias y con 2 transistores ya que queríamos ver cuales son los adecuados para que los motores funcionen correctamente
 
 ## Desafíos y ajustes realizados: Describir los problemas encontrados durante la integración y cómo se solucionaron.

Se tuvieron varios problemas, con las conexiones, con la batería, con las resistencias y transistores como se mencionó antes. Aún no se solucionan todos los problemas, la batería a veces es inestable al igual que las conexiones, y eso esperamos que el profesor nos pueda ayudar. Por otro lado, creemos que las resistencias y los transistores ya funcionan correctamente.
 
 ## Revisión de compatibilidad y sincronización: Mostrar pruebas realizadas para verificar que los componentes funcionen en conjunto de forma fluida.

  <p align="center">
  <img src="https://github.com/Arbandu/Fundbio/blob/8dad817a1beba9b29a5770db753f6e8b04501aed/Imagenes/diagrama%20de%20integracion.jpg" alt="Diagrama de integración">
</p>  

 # Pruebas y Verificación

 ## Descripción de pruebas funcionales: Mostrar cómo se probó cada componente en conjunto y los criterios utilizados.

Las pruebas que se hicieron fueron muy parecidas, los únicos cambios que se hicieron fueron de componentes por el mismo componentes, pero de diferente modelo o voltaje. Ya que cada elemento si o si depende de otro siempre se probaron en conjunto. Los criterios utilizados fueron la cantidad de energía necesaria para que funcione todo correcto 

 ## Resultados de pruebas: Comparación entre los resultados esperados y los obtenidos; mencionar qué ajustes fueron necesarios.

 El resultado que se esperaba era que funcione correctamente todo, pero como se mencionó anteriormente no logramos aún esos resultados, y tenemos que definir aún cuál es el problema y esperamos que el profesor nos pueda ayudar en eso.
 
 ## Evaluación de desempeño: Evaluar si el prototipo cumple con el objetivo establecido en la fase de integración.

Si cumple, ya que nuestro objetivo es que nuestro prototipo cumpla una función de rehabilitación. Nuestros motores darán la señal para que el paciente empiece y para que termine la terapia haciendo los movimientos indicados por el médico, toda esta información se verá a través de la app.

 # Conclusiones y Próximos Pasos
 
 ## Resumen de logros: Explicar qué tan exitosamente se ha completado la integración y qué falta.

Como se mencionó anteriormente lo único que faltaría sería que todos los motores funcionen a la vez, y que funcionen con la batería. Esto sería lo primero ya que una vez que tengamos esto podremos vincularlo con la app que ya tenemos.

 ## Aspectos por mejorar: Discutir qué problemas aún existen o qué componentes requieren ajuste adicional.

El principal problema que se tiene es que el circuito no está funcionando correctamente. Como aún no se sabe exactamente cuál es el problema no sabemos cuál componente requiere ajuste adicional. 

 ## Siguientes fases del desarrollo: Describir los pasos próximos y cómo se enfocarán en mejoras o implementaciones futuras.

El próximo paso sería poder reunirnos con nuestro asesor y que nos pueda ayudar a llegar a la solución de este problema. Una vez que se tengan las mejoras en lo electrónico se pasará al ensamblaje con el diseño 3D que se mandó a imprimir. Una futura mejora podría ser el tema de lo estético, ya que tenemos que ver que sea funcional pero al mismo tiempo se vea bien.
 
