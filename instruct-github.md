# Introducción a Github
- Github es una plataforma de desarrollo colaborativo que aloja proyectos utilizando el sistema de control de versiones Git, además de ofrecer otras funcionalidades, como seguimiento de problemas, peticiones de características, etc.

### Términos comunes en Github
- Github Actions : es una característica de Github que permite automatizar tareas en el flujo de trabajo de desarrollo de software.
- Workflow: Es un archivo YAML que define un conjunto de acciones que se ejecutan en respuesta a eventos del repositorio.
- Event : Es una acción específica que ocurre en un repositorio de Github, como la creación de una solicitud de extracción o el envío de un comentario.
- Job : Unidad de trabajo dentro de un workflow. Un workflow puede tener uno o más jobs, y estos se ejecutan en paralelo o secuencialmente.
- Step : Una acción individual dentro de un job. Un job puede tener uno o más steps, y estos se ejecutan en secuencia.
- Action : Un bloque de código reutilizable que realiza una tarea específica en un step. Las acciones se pueden usar en múltiples repositorios y flujos de trabajo.
- Runner : Es una máquina virtual o contenedor que ejecuta las acciones de un workflow. Los runners pueden ser alojados por Github o por el usuario.
- YAML : Es un formato basado en indentación para representar datos en forma de texto. De una forma legible para huamnos y fácil de interpretar para máquinas.
- actions/checkout@v4 : Es una acción de Github que se utiliza para clonar un repositorio en el runner de Github.
- CI : Continuous Integration (Integración Continua): Se enfoca en automatizar la integración de código de los desarrolladores y las pruebas en un ciclo de desarrollo rápido y constante. ciclo: desarrollador -> repositorio -> CI -> pruebas -> repositorio.
- CD : Continuous Deployment (Despliegue Continuo): Se enfoca en automatizar la entrega de código a un entorno de producción. ciclo: repositorio -> CI -> pruebas -> CD -> producción. 
- .github : Es un directorio especial en un repositorio de Github que contiene archivos de configuración para Github Actions, plantillas de problemas, etc.
- Release : Es una versión específica de un software que se ha empaquetado y se encuentra disponible para su distribución. En Github, las versiones se pueden etiquetar y publicar como "releases".
- Dependabot : Dependabot es un bot que busca y actualiza automáticamente las dependencias de tu proyecto.

### Recursos
https://www.yamllint.com/