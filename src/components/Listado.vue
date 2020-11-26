<template>
  <div class="container">
    <h1>Crea Una Nueva Tarea</h1>
    <!-- ingreso de datos -->
    <div class="input-group mb-3">
      <input type="text" class="form-control boton" placeholder="Ingresa una Tarea..." aria-label="nombre" aria-describedby="button-addon2" v-model="nombre">
      <div class="input-group-append">
        <button class="btn btn-outline-secondary" type="button" @click="mostrarNombre">Agregar</button>
      </div>
    </div>

    <ListaChica :ListaTareas="listaNombres" @eliminarTareas="eliminarTarea"/>
  </div>
</template>

<script>
import ListaChica from './hijosLista/ListaChica'

export default {
  name: 'Listado',
  data() {
        return {
            nombre: '',
            listaNombres: []
        }
    },
    components:{
     ListaChica
    },
    methods: {
        mostrarNombre(){
            if (this.nombre) {
                this.listaNombres.push(this.nombre);
                this.nombre = "";
            } else {
                console.log("no tiene nombre");
            }
        },
        eliminarTarea(index){
            this.listaNombres.splice(index,1);
        }
    },
}
</script>

<!-- CSS -->
<style scoped>
  .boton{
    width: 100px;
  }
</style>
