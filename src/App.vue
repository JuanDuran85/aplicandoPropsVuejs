<template>
  <div>
    <Navbar/>
    <Formulario @enviandoDatos="procesarCurso"/>
    <Tarjetas :dataCurso="datosCursos"/>
    <Footer/>
  </div>
</template>

<script>
import Navbar from './components/NavBar.vue';
import Formulario from './components/Formulario.vue';
import Tarjetas from './components/Tarjetas.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'App',
  data() {
    return {
      datosCursos: []
    }
  },
  components: {
    Navbar,
    Formulario,
    Tarjetas,
    Footer
  },
  methods: {
    procesarCurso(datos){
      console.log(datos);
      this.datosCursos.push(datos);
    }
  },
}
</script>

<style>

</style>
