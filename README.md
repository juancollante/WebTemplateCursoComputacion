# Página académica del curso de CSCI con Jekyll

Este repositorio es un template genérico que sirve para crear una página web de un curso introductorio de Ciencias de la Computación. Estamos utilizando  Jekyll y GitHub Pages para despliegue en la web.

## Despliegue

Hay sólo unos pocos pasos para crear un nuevo sitio web del curso a partir de este repositorio.

* Determina el subdirectorio que utilizarás para este curso. Por ejemplo, "curso_###_Introduccion a las ciencias de la computacion".

* Usa este repositorio como template para hacer tu nuevo repositorio, nombrándolo exactamente con el nombre de tu subdirectorio elegido. Tu repositorio puede ser público o privado.

* Edita el archivo _config.yml en la línea 27, cambiando baseurl por tu subdirectorio elegido.

* Configura el repositorio para que aparezca como un sitio web de GitHub Pages. 

¡Listo! Tu sitio web del curso debería ser visible en https://<username>.github.io/<subdir>.

## Contenido

Una vez que tu repositorio del curso esté creado y visible en la web, es hora de actualizar el contenido.

### Imagen de Fondo

La forma más sencilla de establecer la imagen de fondo es copiar una nueva imagen en el directorio assets/images y nombrarla jumbo-background.jpg. Imágenes más grandes son mejores y tendrán menos pixeles en pantallas grandes.

Para un tipo diferente de imagen o para que tenga otro nombre, necesitarás cambiar el nombre del archivo en las definiciones de la clase .jumbotron en el archivo assets/css/main.css para que el atributo src muestre tu archivo..

### Descripción, Número de Curso, Título y Semestre

El archivo _config.yml contiene varios elementos que se pueden editar para personalizar el curso para tu contenido.

Primero, reemplaza la description actual con la descripción de catálogo de tu curso. Asegúrate de que está indentada para seguir el formato YAML.

Luego, cambia el codigo de tu curso y el semestre, por ejemplo, 2024-2. Estos aparecerán en la página web en la parte superior izquierda de la barra de navegación.

Finalmente, el titulo del curso debería ser editado para que coincida con el nombre del catálogo, por ejemplo, Fundamentos de la Ciencia de la Computación.

### Barra de navegacion

La barra de navegación presenta los enlaces en la parte superior derecha del encabezado en cada página. Los enlaces simples tienen un campo page y url, mientras que los grupos de enlaces se denotan con un campo title y una lista subfolderitems de enlaces simples.

### Instructores y Ofertas

La siguiente sección de _config.yml define la informacion del instructor para el curso. Un instructor tiene un id, nombre, dirección de email, enlace web, número de telefono, y enlace de horario de atención. Esta información se muestra ya sea en o cerca del jumbotron en el encabezado de la página principal.

Luego, secrea la lista de tutores disponibles para el curso,con campos para nombre, salon, horario, e id del tutor.

### Recursos

Los recursos proporcionados a los estudiantes, como enlaces a software o libros de texto, se enumeran a continuación en la lista resources. Cada recurso tiene un nombre, una imagen utilizada para una referencia visual fácil, y un url para enlazar al recurso. Estos se pueden mostrar en una fila, con un máximo de cuatro por fila, usando la plantilla que se encuentra en _includes\resources.html.

Recursos adicionales en diferentes categorías se pueden crear siguiendo la misma estructura, como se muestra con la sección extra-resources que se muestra en la página index.md con el encabezado de Recursos Opcionales.

### Laboratorios, Tareas, y Proyectos

Las asignaciones de los estudiantes, como laboratorios, tareas y proyectos, deben utilizar el layout work.html. Es útil organizar los laboratorios, tareas y proyectos en sus propios directorios.

Los archivos sample-lab.md y sample-project.md son buenos ejemplos de cómo usar markdown para escribir una asignación. La frontmatter al principio de la página es procesada por el layout para mostrar el título y el número en la parte superior de la página web.
    ---
    layout: Tarea
    type: Lab
    num: 4
    worktitle: Calculos y estadisticas
    ---

Esto se puede editar para una tarea específica, y aumentar para incluir cualquier información que desees como variables dentro de tu tarea, como las fechas de vencimiento en la página de proyecto de ejemplo.

Se incluyeron cuatro alertas para ayudar a resaltar las partes clave de las asignaciones. Pueden ser para secciones de warning, tip, note o important, con su origen en la carpeta _includes, y se incluyen usando la siguiente sintaxis

    {% include important.html content="Asegurate de entregar tu tarea antes del 20 de abril." %}
