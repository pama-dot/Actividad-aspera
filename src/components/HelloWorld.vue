<template>
  <div>
    <input class="text" placeholder="usuario" v-model="usuario">
    <input class="text" placeholder="password" v-model="password">
    <button @click="asignarDatos()">Enviar</button>
    <div v-show="mensaje" :style="`color:${color}`">{{ mensaje }}</div>
  </div>  
</template>

<script>
export default {
  name: 'HelloWorld',
  data: () => ({
    usuario: '',
    password: '',
    mensaje: '',
    color: ''
  }),
  methods: {
    asignarDatos(){
     if(!this.usuario && !this.password) {
       this.mensaje = "Ambos estan vacios"
       this.color = "red"
     }
     else if (!this.usuario || !this.password) {
       this.mensaje = "Alguno esta vacio"
       this.color = "red"
     }
     else {
       this.mensaje = "Se ha iniciado sesion con exito"
       this.color = "green"
     }
    }
  },
  computed: {
    nombreCompleto(){
       return `${this.nombre} ${this.apellido}`
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
