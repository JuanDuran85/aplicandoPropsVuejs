<template>
  <div>
    <Navbar/>
    <Formulario/>
    <Footer/>
  </div>
</template>

<script>
import Navbar from './components/NavBar.vue';
import Formulario from './components/Formulario.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'App',
  components: {
    Navbar,
    Formulario,
    Footer
  }
}
</script>

<style>

</style>
