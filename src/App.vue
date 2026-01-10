<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> |
    <router-link to=" `/hola-mundo/${idEstudiante}` ">Hola Mundo</router-link> |
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

/*Manejar dentro variables en las URLs, son y sirven para:
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
