<template>
  <section class="my-5 container">
    <h1 class="text-center">Ingresa el curso</h1>
    <form>
      <div class="form-group">
        <label for="titulo">Titulo del Curso</label>
        <input type="text" class="form-control">
      </div>
      <div class="form-group">
        <label for="imagen">Enlace de Imagen</label>
        <input type="text" class="form-control">
      </div>
      <div class="form-group">
        <label for="descripcion">Descripción del curso</label>
        <textarea class="form-control" rows="3"></textarea>
      </div>
      <button type="submit" class="btn btn-danger btn-lg">Reset</button>
      <button type="submit" class="btn btn-success mx-2 btn-lg">Enviar</button>
    </form>
  </section>
</template>

<script>
export default {
  name: 'Formulario',
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
