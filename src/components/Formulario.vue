<template>
  <section class="my-5 container">
    <h1 class="text-center">Ingresa el curso</h1>
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
  </section>
</template>

<script>
export default {
  name: 'Formulario',
  data() {
    return {
      titulo: '',
      imagen: '',
      descripcion: '',
      id: 1
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
      } else {
        console.log("No hay datos...");
      }
    }
  },
}
</script>