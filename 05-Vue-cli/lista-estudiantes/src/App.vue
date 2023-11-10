<template>
  <h2>{{titulo}}</h2>
  <div class="container">
    <div class="form">
      <div class="form-group">
        <label>Nombre</label>
        <input type="text" class="form-control" v-model="registro.nombre">
      </div>
      <div class="form-group">
        <label>Centro</label>
        <input type="text" class="form-control" v-model="registro.colegio">
      </div>
      <br>
      <button class="btn btn-primary" @click="agregarEstudiante">Guardar</button>
    </div>
    <hr>
    <div class="row">
      <div class="col-5" v-for="registro in registros" :key="registro">
        <div class="card">
          <div class="form-group">
            <h2>{{registro.nombre}}</h2>
            <hr>
            <p>{{registro.colegio}}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>


export default {
  name: 'App',
  data(){
    return{
      titulo: 'Pruebitas Vue con proyectos',
      registro: {
        nombre: '',
        colegio: ''
      },
      registros: [
        {
          nombre: 'Kiko Rivera',
          colegio: 'plaiaundi'
        }
      ]
    }
  },
  methods: {
    agregarEstudiante: function() {
      const {nombre, colegio} = this.registro;
      this.registros.push({
        nombre,
        colegio
      })
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
