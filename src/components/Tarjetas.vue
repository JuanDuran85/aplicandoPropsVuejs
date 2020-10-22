<template>
  <section class="container my-5">
      <section class="row">
          <section class="col-12 col-sm-12 col-md-6 col-lg-4 col-xl-4" v-for="(curso,index) in dataCurso" :key="index">
            <div class="card">
                <img :src="curso.imagen" class="card-img-top" :alt="curso.id">
                <div class="card-body">
                    <h5 class="card-title">{{curso.titulo}}</h5>
                    <p class="card-text">{{curso.descripcion}}</p>
                    <a href="#" class="btn btn-primary" @click.prevent="eliminarCurso(index)">Eliminar</a>
                </div>
            </div>
          </section>
      </section>
  </section>
</template>

<script>
export default {
    name: 'Tarjetas',
    props: {
        dataCurso: {
            type: Array,
            required: true
        }
    },
    methods: {
        eliminarCurso(index){
            this.$emit('eliminarCurso', index);
        }
    },
}
</script>

<style scoped>
    img {
        max-width: 150px;
        max-height: 150px;
    }
</style>