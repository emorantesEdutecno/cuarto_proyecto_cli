<template>
    <div id="FormularioComponent">
        <h1>Formulario Factura</h1>
        <br>
            <form>
                <label for="txtNombre">Nombre:</label>
                <input id="txtNombre" type="text" v-model="losDatos.elNombre"> <br>
                <label for="txtApellido">Apellido:</label>
                <input id="txtApellido" type="text" v-model="losDatos.elApellido"><br>
                <input type="submit" v-on:click.prevent="enviarAlPadre" value="Enviar" >
            </form>
    </div>
</template>


<script>
export default{
    name:'FormularioComponent',
    data:function(){
        return{
            losDatos:{
                elNombre: '',
                elApellido:'',
            },

        }
    },
    methods:{
        enviarAlPadre: function(){
            this.$emit('datosForm', this.losDatos);
        },
    },

}
</script>

<style scoped>
    #FormularioComponent{

    }
</style>