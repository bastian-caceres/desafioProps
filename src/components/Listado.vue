<template>
  <div class="container">
    <h1>Crea Una Nueva Tarea</h1>
    <!-- ingreso de datos -->
    <div class="input-group mb-3">
      <input type="text" class="form-control boton" placeholder="Ingresa una Tarea..." aria-label="tarea" aria-describedby="button-addon2" v-model="tarea">
      <div class="input-group-append">
        <button class="btn btn-outline-secondary" type="button" @click="mostrarTarea">Agregar</button>
      </div>
    </div>

    <ListaChica :ListaTareasH="listaTareasP" @eliminarTareas="eliminarTarea"/>
  </div>
</template>

<script>
import ListaChica from './hijosLista/ListaChica'

export default {
  name: 'Listado',
  data() {
        return {
            tarea: '',
            listaTareasP: []
        }
    },
    components:{
     ListaChica
    },
    methods: {
        mostrarTarea(){
            if (this.tarea) {
                this.listaTareasP.push(this.tarea);
                this.tarea = "";
            } else {
                console.log("no tiene nombre");
            }
        },
        eliminarTarea(index){
            this.listaTareasP.splice(index,1);
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
