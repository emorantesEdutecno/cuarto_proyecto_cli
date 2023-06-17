<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p> Contador: {{ contador }}</p>
    <button v-on:click="contador+=1" >Presioname</button>
    <hr>
    <p>datos evento: {{  datosEvento }}</p>
    <button v-on:click="verEvento">Ver datos del evento click</button>
 
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
  },
  data: function(){
    return{
      contador: 0,
      datosEvento: '',
    }
  },
  methods:{
    verEvento: function(event){
      console.log(event);
      this.datosEvento = event.target.tagName;
    }
  },
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

.hello{
  background-color: darkgoldenrod;
}
</style>
