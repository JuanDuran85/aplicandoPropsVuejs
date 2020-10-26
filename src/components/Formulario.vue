<template>
  <section class="my-5 container">
    <h1 class="text-center">Ingresa el curso</h1>
    <h4>{{conversionTexto}}</h4>
    <form @submit.prevent="enviarData">
      <div class="form-group">
        <label for="titulo">Titulo del Curso</label>
        <input type="text" class="form-control" v-model="titulo">
      </div>
      <div class="form-group">
        <label for="imagen">Enlace de Imagen</label>
        <input type="text" class="form-control" v-model="imagen">
      </div>
      <div class="form-group">
        <label for="descripcion">Descripción del curso</label>
        <textarea class="form-control" rows="3" v-model="descripcion"></textarea>
      </div>
      <button type="reset" class="btn btn-danger btn-lg">Reset</button>
      <button type="submit" class="btn btn-success mx-2 btn-lg">Enviar</button>
    </form>
    <div v-if="largoTitulo > 0">
      <p>El largo del titulo del curso es: {{largoTitulo}} </p>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Formulario',
  data() {
    return {
      mensaje: 'Mensaje desde Data',
      titulo: '',
      imagen: '',
      descripcion: '',
      id: 1
    }
  },
  computed: {
    conversionTexto(){
      return this.mensaje.toLowerCase();
    },
    largoTitulo(){
      return this.titulo.length;
    }
  },
  methods: {
    enviarData(){
      if (this.titulo && this.descripcion && this.imagen) {
        let dataCurso = {
          titulo: this.titulo,
          descripcion: this.descripcion,
          imagen: this.imagen,
          id: this.id++
        };
        
        this.$emit('enviandoDatos',dataCurso);
        this.imagen = "";
        this.titulo = "";
        this.descripcion = "";
      } else {
        console.log("No hay datos...");
      }
    },
    mostrarVentana(){
      alert("Se esta viendo todo en el HTML...");
    }
  },
  beforeCreate() {
    console.log("Antes de crear desde formulario");
  },
  created() {
    console.log("creado desde formulario");
    this.mostrarVentana();
  },
  beforeMount() {
    console.log("Antes de montar desde formulario");
  },
  mounted() {
    console.log("montado todo desde formulario...");
  },
  beforeUpdate() {
    console.log("antes de actualizar desde formulario...");
  },
  updated() {
    console.log("Actualizado desde formulario");
  },
}
</script>