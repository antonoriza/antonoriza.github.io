---
title: "El stack tecnológico de este website"
date: 2024-01-14
draft: false
toc:
  enable: false
  auto: false
linkToMarkdown: false
share:
      enable : true
      Twitter : true
      HackerNews : true
      Reddit : true
      Whatsapp : true
      Facebook: False
      Line : false
      Weibo : false
---
¡Hola! Si me conoces por mi trabajo secundario relacionado con la construcción de sitios web, podrías asumir que este sitio está hecho con WordPress.

¡Pero no! En mi camino para convertirme en escritor, quería aprender algo nuevo (WordPress ya era demasiado fácil para mí) y experimentar la sensación mágica que viene con aprender y crear algo nuevo.

Para ser honesto, mi mente de hacker inicialmente pensó, "Vamos a construir un blog desde cero usando un lenguaje de programación esotérico, crear un marco sólido, lanzarlo como código abierto al público y finalmente, construir el blog sobre él". Desde otra perspectiva, también consideré algunas excelentes opciones centradas en la experiencia de escritura, como Bearblog, Substack y Medium.

Después de oscilar entre extremos, desde la "experiencia completa de desarrollador" hasta la "experiencia completa de escritor", llegó el momento de encontrar un equilibrio entre ambos y elegir la mejor manera de crear un blog. Así que comencé a explorar pilas y marcos populares disponibles.

Entre las muchas pilas disponibles (como MEAN, MEARN, LAMP, Django, Ruby on Rails, LAMP), quería elegir algo "potente". Esto claramente era un asunto subjetivo, así que hice una lista de características que quería en mi sitio web (requisitos generales, si se pueden llamar así):

- Un blog
- Una página "sobre mí"
- Una vista minimalista
- Iconos de redes sociales
- Soporte incorporado para páginas multilingües
- Páginas de carga rápida
- Adaptabilidad móvil
- Mantenimiento y escalabilidad sencillos
- Un dominio personalizado
- No necesidad de pagar por el alojamiento

Está claro que lo que tenía en mente era simple (solo contenido estático, sin bases de datos, sin backend sofisticado). Entonces, ¿por qué querría usar una pila "potente"? ¡Sería una sobreingeniería! Podría crear fácilmente un proyecto simple usando HTML y CSS (o incluso usar una plantilla pura de HTML, CSS), ¡y listo!

Esto plantea un punto interesante. Si eres un ingeniero/creador/desarrollador, es posible que estés de acuerdo en que nos convertimos en ingenieros/creadores/desarrolladores porque disfrutamos construyendo cosas y resolviendo problemas complejos. A veces, es emocionante imaginar una solución compleja para un problema persiguiendo la "solución última para todos los casos relacionados con ello".

Sin embargo, además de que soy escéptico de que exista una "solución última para todos los casos" para un problema, es muy común ver a las personas perderse en el problema, perdiendo el enfoque en otros parámetros importantes, como el tiempo disponible, la viabilidad y la complejidad... y paradójicamente eso crea un problema más importante porque te desconectas de la solución impactante y de los resultados de lo que estás trabajando.

Crear y entregar algo puede convertirse en una actividad interesante o en una actividad sisifiana. Al final, como creador, debes encontrar la satisfacción en el acto de lanzar iteraciones estables de tu creación a lo largo del tiempo de la misma manera que lo encuentras en el acto de resolver problemas complejos.

Así que, finalmente, había hecho algunos avances... había decidido crear mi blog con HTML, CSS y JS puros. Pero no estaba contento con esa elección. Aunque la decisión de usar HTML, CSS y JS puros es loable por la personalización completa que proporciona, incorporar un marco podría ser una idea mejor y una elección estratégica para superar los obstáculos comunes del desarrollo relacionados con el tiempo de desarrollo, agrupar la complejidad involucrada, mejorar la eficiencia y mejorar el rendimiento general de tu blog a medida que evoluciona.

Así que pasé casi dos semanas (en mi tiempo libre) leyendo por toda la web sobre marcos hasta que encontré un enfoque arquitectónico llamado "Jamstack" (JavaScript, APIs, Markdown) que me gustó. En términos sencillos, simplifica el flujo de trabajo de desarrollo desacoplando el front-end del back-end, precompilando/prerrenderizando gran parte del contenido antes de que el HTML llegue al navegador, creando despliegues limpios y atómicos, sirviendo un sitio web/aplicación estáticamente en el borde.

Para mis planes, parece ofrecer una interesante combinación de experiencia de autor y de desarrollador. Para comenzar a escribir, todo lo que tienes que hacer es crear un nuevo archivo Markdown en el directorio adecuado y empezar a escribir, y si estás en modo desarrollador, puedes agregar tus propias personalizaciones al sitio web.

Una vez que hayas terminado, tienes la capacidad de implementar el sitio web directamente desde un repositorio Git para compartirlo con el mundo. Alojar un sitio estático es versátil y a menudo bastante asequible, ya que se puede alojar en diversas plataformas. Como tratamos exclusivamente con archivos puramente estáticos, evitamos las limitaciones típicas de implementación asociadas con la hospedación de lenguajes dinámicos del lado del servidor junto con un servidor de base de datos.

Este enfoque no es nuevo; para ser honesto, la idea de desacoplar la capa de presentación de la lógica comercial ya existía. Pero Jamstack es básicamente una forma de rebautizar los conocidos sitios estáticos, diciendo que deberías generar las páginas que estás sirviendo y enviarlas a una red CDN para la velocidad de Time to First Byte (TTFB). El objetivo es eliminar el tiempo que pasa en un servidor mientras el visitante espera a que se cargue el front-end.

Además, aunque este enfoque estático puede parecer simple, también ofrece mucha flexibilidad. Aún puedes hacer que tu sitio web sea dinámico mediante llamadas a API para cualquier cosa que necesite acceder a una base de datos, ya sea que estés siguiendo un enfoque sin servidor o con servidor. Entonces, Jamstack no significa exclusivamente "contenido estático"... Es una forma de mostrar a las personas en el desarrollo web que deberíamos hacer más cosas de manera estática cuando sea posible y separar los componentes dinámicos en sus propias API. De esta manera, mejoramos el rendimiento, la experiencia del usuario (UX) de la aplicación y, por supuesto, el SEO.

Después de buscar entre los diferentes SSG disponibles, decidí usar Hugo. ¿Por qué Hugo? Bueno, dos puntos importantes distinguen a Hugo de la mayoría de otras opciones de generadores de sitios estáticos. En primer lugar, está entre los pocos generadores escritos en el lenguaje de programación Go, y como aprendí Go hace 2 años, quería poner en práctica ese conocimiento en un proyecto real (algunos aspectos de construir incluso plantillas básicas de Hugo requieren al menos un conocimiento básico del lenguaje Go). En segundo lugar, prioriza tiempos de compilación extremadamente rápidos. Esto puede ser una consideración crucial, ya que los tiempos de compilación con otros motores pueden convertirse en un impedimento significativo a medida que aumenta el tamaño de un sitio (puede compilar una sola página web en milisegundos y un sitio web completo en segundos).

Instalar Hugo es en su mayoría cuestión de descargar el ejecutable binario adecuado para tu plataforma desde la página de lanzamientos. Hugo es compatible con Windows, OS X, Linux y FreeBSD. Estoy usando Linux Mint en mi computadora actual, así que primero instalé Homebrew y luego instalé Hugo con: `brew install hugo`.

Una vez que Hugo está instalado, es hora de generar tu sitio web. Para hacerlo, puedes crearlo desde cero usando el comando "hugo new site [nombre del proyecto]" (lo que creará tu estructura básica de carpetas y archivos y tendrás que codificar tus propios diseños en la carpeta "layouts") o puedes usar un tema de Hugo. En mi caso, encontré el tema "love it" que me encantó pero quería personalizar, así que lo bifurqué y lo renombré a "HateIt" (quería sentirme rebelde :’v).

Es importante notar que Hugo ofrece la opción de especificar el tipo de formato de datos que te gustaría usar al generar nuevos archivos. Por defecto, Hugo usa TOML (por su legibilidad y simplicidad), pero puedes usar archivos Yaml o incluso Json. También, al diseñar diseños personalizados para tu sitio estático en Hugo, es común emplear la biblioteca html/template de Go, ya que esto permite a los usuarios dar forma a la estructura y presentación de su contenido mediante la creación de plantillas personalizadas utilizando la sintaxis de templating de Go (la documentación actual sobre esto no es realmente fácil de leer, pero es un buen desafío).

Antes de continuar, también es importante notar que Hugo gestiona la configuración básica de tu sitio web en el archivo "config.toml", que toma su plantilla del archivo del mismo nombre pero en el directorio del tema. Así que echa un vistazo a ese archivo (si estás usando un tema, generalmente todos lo usan) si deseas realizar algunas personalizaciones básicas sin modificar directamente los archivos html, css y js internos.

Entonces, después de haber creado mi proyecto Hugo, agregado mi tema personalizado "Hate IT" como un submódulo de Git dentro del directorio "themes" y configurado el archivo "config.toml", probé con una entrada ficticia... ¡y funcionó! (Hugo también incluye un servidor web local para probar tu sitio localmente), así que el siguiente paso fue alojarlo para que todos pudieran acceder a mi sitio web.

Hay muchas opciones disponibles para alojar tu sitio web Jamstack de forma gratuita. Por supuesto, puedes pagar por un servicio de alojamiento, pero ¿por qué hacerlo cuando hay opciones gratuitas disponibles y con ofertas realmente buenas en los tiempos de actividad del SLA? Consideré dos opciones: Netlify y Github Pages. Decidí usar "GitHub Pages" porque me gusta GitHub :D

Subí mi repositorio del sitio web Hugo a GitHub (aunque no lo había mencionado antes, he estado usando Git desde que creé mi sitio web Hugo, jeje). Es importante destacar que este repositorio debe llamarse "[nombre de usuario].github.io" (por las reglas de GitHub). Luego configuré una acción de GitHub para implementarlo cada vez que hice un nuevo cambio, ¡y voilà, mi sitio web estaba en vivo! Por supuesto, más adelante, conecté un dominio personalizado porque no era fanático de usar la larga URL gratuita que proporcionaba GitHub.

Realmente espero que hayas disfrutado de esta publicación. Si te fue útil, me complace. Considera compartirlo con otros o citarlo si, algún día, usas contenido de estas palabras. ¡Feliz hacking, juakers! 

Traducido del artículo en ingles mediante ChatGPT (luego lo pondre a español pero ya es noche y quiero publicar esto ya porque rapido es mejor que perfecto, almenos para este blog).