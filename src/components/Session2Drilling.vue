<template>
    <h1>{{ msg }}</h1>
    <form v-on:submit.prevent="agregarTarea">
        <input type="text" v-model="tarea">
        <input type="submit" :value="indiceEdicion===-1 ? 'Agregar Tarea' : 'Guardar Cambios'">
    </form>
    <hr>
    <h2>Listado de Tareas</h2>
    <ul>
        <li v-for="(t, index) in listadoTareas" :key="index">
            {{ t }}
            <button v-on:click="editar(index)">Editar</button>
            <button @click="eliminar(index)">Eliminar</button>
        </li>

    </ul>
    
</template>

<script>
export default{
    name:'Session2Drilling',
    props:{
        msg:String,
    },
    data(){
        return{
            tarea:'',
            listadoTareas: [],
            edad: 0,
            indiceEdicion:-1,
        };
    },
    methods:{
        agregarTarea(){
            if (this.indiceEdicion=== -1) {
                this.listadoTareas.push(this.tarea);
            } else {
                this.listadoTareas.splice(this.indiceEdicion, 1, this.tarea);
                this.indiceEdicion = -1;
            } 
            this.tarea = '';
        },
         editar(index){
            this.tarea = this.listadoTareas[index];
            this.indiceEdicion = index;
         },
         eliminar(index){
            this.listadoTareas.splice(index,1);
            if (this.indiceEdicion === index) {
                this.indiceEdicion = -1;
                this.tarea = '';
            }
        }
    }
}
</script>

<style>
    ul {
       list-style: none;
       color: #b008d1;
       li{
        padding: 5px;
       }
       button{
        margin: 5px;
       }
    }
</style>