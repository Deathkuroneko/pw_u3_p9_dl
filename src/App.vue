<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> |
    <router-link :to="`/hola-mundo/${idEstudiante}`">Hola Mundo</router-link> |
    <router-link to="/pregunta">Pregunta</router-link> |
    <router-link to="/pokemon">Pokemon</router-link>
  </nav>
  <input v-model="idEstudiante" type="text">
  <router-view/>
</template>

<script>
  export default {
    data() {
      return {
        idEstudiante: null,
      };
    },
  };
</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>

APIs: es un contrato (conjunto de definiciones, especificaciones, protocolos, salidas, entrdas, etc.) para que dos aplicaciones tecnologicas se comuniquen o integren entre si,
una API encapsula toda la logica que utliza para coumplir con el contrato, y expone solo lo necesario para que otras aplicaciones puedan interactuar con ella 
sin necesidad de conocer su implementacion interna.
APIs: es un contrato (conjunto de definiciones, especificaciones, protocolos, salidas, entrdas, etc.) para que dos aplicaciones tecnologicas se comuniquen o integren entre si,
una API encapsula toda la logica que utliza para coumplir con el contrato, y expone solo lo necesario para que otras aplicaciones puedan interactuar con ella 
sin necesidad de conocer su implementacion interna.
Por su estilo arquitectonico arquitectura existes:
1. APIs SOAP: utilizan el protocolo SOAP (Simple Object Access Protocol) y se basan en XML para el intercambio de mensajes entre aplicaciones.
2. APIs GraphQL: permiten a los clientes solicitar solo los datos que necesitan, utilizando un lenguaje de consulta flexible.
                  Lenguaje de consulta para clientes, donde el cliente define lo que necesita y el servidor responde con exactamente esos datos.
3. APIs RESTful: son APIs que siguen los principios REST y utilizan los verbos HTTP (GET, POST, PUT, DELETE) para realizar operaciones sobre recursos.
              REST: Representational State Transfer, es un estilo arquitectonico para diseñar servicios web.
              Este estilo exige que se cumplan ciertos principios:
              1. El recurso: todo en REST se considera un recurso, que se identifica mediante una URL unica.
              2. Cliente - servidor: la comunicacion se realiza entre un cliente (que consume el servicio) y un servidor (que provee el servicio).
              3. Sin estado (statelessness): cada solicitud del cliente al servidor debe contener toda la informacion necesaria para entender y procesar la solicitud, 
              sin depender del estado del servidor. Es 1 a 1, el servidor no guarda informacion del cliente entre solicitudes. (son independientes)
              4. Uso correcto de los verbos HTTP: cada verbo HTTP tiene un proposito especifico en REST.
                  - GET: para obtener recursos. (hacer consultas)
                  - POST: para crear nuevos recursos. (hacer creaciones o insertar un recurso)
                  - PUT: para actualizar recursos existentes. (actualizar o modificar un recurso)
                  - PATCH: para actualizaciones parciales de recursos. (actualizar o modificar parcialmente un recurso)
                  - DELETE: para eliminar recursos. (hacer eliminaciones)
              5. Representaciones: nose trabaja directamente con los recursos, sino con sus representaciones (JSON, XML, HTML, etc.)
              6. Codigos de estado HTTP: se utilizan codigos de estado HTTP para indicar el resultado de una solicitud (200 OK, 404 Not Found, 500 Internal Server Error, etc.)
              7. Cacheable: que la api pueda manejar el almacenamiento en cache de las respuestas para mejorar el rendimiento y reducir la carga en el servidor.
              8. Por capas: la api debe estar diseñanda en capas, permitiendo la escalabilidad y la modularidad del sistema, separando las responsabilidades.
              Logica de negocio o service, acceso a datos o repository, controladores o controllers, etc.
4. APIs GRPC: utilizan el protocolo gRPC (Google Remote Procedure Call) para la comunicacion eficiente entre aplicaciones, utilizando HTTP/2 y Protobuf como formato de serializacion.
              Siendo muy eficientes para el backend interno.
5. Apis Asinconicas: permiten la comunicacion entre aplicaciones de manera asincronica, utilizando mecanismos como colas de mensajes o eventos.
                      Su principal ventaja es que genera un desaclopamiento entre los componentes que se comunican, mejorando la escalabilidad y la resiliencia del sistema.

MicroProfile: es un conjunto de especificaciones para la construcion de APIs diseñadas para desarrollar aplicaciones microservicios en Java.
              Proporciona un conjunto de herramientas y librerias que facilitan la creacion, despliegue y gestion de microservicios, 
              incluyendo funcionalidades como configuracion, tolerancia a fallos, seguridad, monitorizacion, entre otras.
              pero por si sola no tiene una implementacion concreta, sino que es un conjunto de especificaciones que pueden ser implementadas por diferentes frameworks o servidores de aplicaciones.
Otras especifaciones para microservicios en Java:
1. Spring Boot: framework popular para desarrollar aplicaciones Java, que facilita la creacion de microservicios con configuracion automatica y 
                una amplia gama de funcionalidades integradas.
2. Eclipse Vert.x: framework ligero y reactivo para construir aplicaciones microservicios en Java, que ofrece un modelo de programacion basado en eventos
                  y una alta escalabilidad.
3. Dropwizard: framework que combina varias librerias y herramientas para desarrollar aplicaciones microservicios en Java, 
                proporcionando una configuracion sencilla y un conjunto de funcionalidades listas para usar.
4. Helidon: framework ligero para construir microservicios en Java, que ofrece dos enfoques: Helidon SE (programacion reactiva) y Helidon MP (MicroProfile).
5. Quarkus: framework moderno y optimizado para desarrollar microservicios en Java, que se enfoca en el rendimiento y la eficiencia, 
            con tiempos de arranque rapidos y bajo consumo de memoria.
6. Jpa: Java Persistence API, es una especificacion de Java para el mapeo objeto-relacional (ORM) y la gestion de datos en aplicaciones Java.
          Proporciona una forma estandarizada de interactuar con bases de datos relacionales utilizando objetos Java.
          Algunas implementaciones populares de JPA son Hibernate, EclipseLink y OpenJPA.

Quarkus / SprintBoot: aunque Quarkus se demore mas en compilar que SpringBoot, una vez compilado, Quarkus tiene un tiempo de arranque 
                    mucho mas rapido y un consumo de memoria mucho menor que SpringBoot, lo que lo hace ideal para entornos de microservicios 
                    y serverless donde el rendimiento y la eficiencia son cruciales.

Manejar dentro variables en las URLs, son y sirven para:
1. Hacer las rutas dinámicas.
2. Pasar parámetros a los componentes a través de la URL.
3. Mejorar la experiencia del usuario al permitir URLs personalizadas.
4. Facilitar la navegación y el acceso a diferentes vistas o datos específicos dentro de una aplicación

path variable es: cuando se envia una varible directamente en la URL o path
                  (ejemplo: /usuario/ -> usuario/1 o usuario/juan), es un segmento
                  de la ruta que puede variar.
request params o query params es: cuando se envia una variable despues de una barra diagonal (/) en la URL
                                (ejemplo: /usuario/1 o usuario/juan), es parte de la ruta que se utiliza para identificar un recurso específico.
                                En Vue Router, se accede a estos parámetros
query variable es: cuando se envia una variable despues del signo de interrogacion (?) en la URL
Cuando uso path variable o request params: cuando la variable es esencial para identificar un recurso específico,
                                          usado como identificador único. (/estudiantes(parte general)/1234 (parte variable que identifica al estudiante))
Cuando uso query variable: cuando la variable es opcional o se utiliza para filtrar o modificar, no es esencial para identificar un recurso específico.
                          (/estudiantes?anio=2023&mes=marzo)*/
path variable vs query variable: 
path variable: es una parte fija de la ruta que identifica un recurso específico.
query variable: es una parte opcional de la ruta que se utiliza para filtrar o modificar datos.