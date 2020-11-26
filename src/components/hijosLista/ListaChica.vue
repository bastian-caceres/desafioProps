<template>
    <div class="container">  
        <!-- lista de tareas  -->
        <table class="table table-dark mt-5 text-center" v-show="ListaTareasH.length > 0">
        <thead>
            <tr>
            <th colspan="3" class="text-center">Lista de Tareas Agregadas </th>
            </tr>
            <tr>
            <th>#</th>
            <th>Tarea</th>
            <th>Accion</th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="(tarea,index) in ListaTareasH" :key="index">
            <td>{{index+1}}</td>
            <td>{{tarea}}</td>
            <td><button type="button" class="btn btn-danger btn-sm" @click="eliminarName(index)">Eliminar</button></td>
            </tr>
            <tr>
            <th colspan="3" class="text-center">Tareas Agregados: {{ListaTareasH.length}}</th>
            </tr>
        </tbody>
        </table>
    </div>
</template>

<script>
export default {
    name: 'ListaChica',
    props: {
        ListaTareasH: {
            type: Array,
        }
    },
    methods: {
        eliminarName(index){
            this.$emit('eliminarTareas',index);
        }
    },
}
</script>

<style>

</style>