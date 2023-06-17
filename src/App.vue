<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Bienvenido a VueJS"/>

    <p>Nombre: {{ objetoRecibido.nombreRecibido }}</p>
    <p>Apellido: {{  objetoRecibido.apellidoRecibido }}</p>

    <hr>
    <div id="contenedorPadre">
      <div id="contenedorFormulario">
          <FormularioComponent
              v-on:datosForm="recibirDatosForm"
          />
      </div>
      <div id="contenedorDatos">
        <DatosComponent 
          v-bind:unNombre="objetoRecibido.nombreRecibido"
          v-bind:unApellido="objetoRecibido.apellidoRecibido"
        />
      </div>
    </div>

  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';
import FormularioComponent from '@/components/FormularioComponent.vue';
import DatosComponent from '@/components/DatosComponent.vue';

export default {
  name: 'App',
  components: {
    HelloWorld,
    FormularioComponent,
    DatosComponent
  },
  data: function(){
    return{
        objetoRecibido:{
          nombreRecibido:'',
          apellidoRecibido:'',
        },
    }
  },
  methods:{
    recibirDatosForm:function(objetoDatos){
        this.objetoRecibido.nombreRecibido = objetoDatos.elNombre;
        this.objetoRecibido.apellidoRecibido = objetoDatos.elApellido;
    }
  },
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

#contenedorPadre{

}

#contenedorFormulario{
  width: 49%;
  background-color: aqua;
  display: inline-block;
}

#contenedorDatos{
  width: 49%;
  background-color: greenyellow;
  display: inline-block;
}
</style>
