<template>
    <div id="DatosComponent">
        <h1>Datos Factura</h1>
        <p>Factura para : {{ unNombre }} {{  unApellido }}</p>
        <p>Fecha: {{  fechaActual  }}</p>
        <button v-on:click="generarFecha">Generar Fecha</button>
    </div>
</template>

<script>
export default{
    name:'DatosComponent',
    props: ['unNombre', 'unApellido'],
    data: function(){
        return{
            fechaActual: '',
        }
    },
    methods:{
        generarFecha: function(){
            const tiempoTranscurrido = Date.now();
            const hoy = new Date(tiempoTranscurrido);
            this.fechaActual = hoy.toDateString(); // "Sun Jun 14 2020"
        }

    },
}
</script>


<style scoped>

</style>