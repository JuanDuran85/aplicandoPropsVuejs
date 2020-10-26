<template>
  <div>
    <Navbar/>
    <Formulario @enviandoDatos="procesarCurso"/>
    <Tarjetas :dataCurso="datosCursos" @eliminarCurso="borrarCurso"/>
    <Footer/>
<!--     <button @click="destruir">destruir</button> -->
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
    },
    borrarCurso(index){
      this.datosCursos.splice(index,1);
    },
/*     destruir(){
      this.$destroy();
    } */
  },
  beforeCreate() {
    console.log("Antes de crear");
  },
  created() {
    console.log("creado");
  },
  beforeMount() {
    console.log("Antes de montar");
  },
  mounted() {
    console.log("montado todo...");
  },
  beforeUpdate() {
    console.log("antes de actualizar...");
  },
  updated() {
    console.log("Actualizado");
  },
  beforeDestroy() {
    console.log("antes de destruir");
  },
  destroyed() {
    console.log("destruido");
  },
}
</script>

<style>

</style>
