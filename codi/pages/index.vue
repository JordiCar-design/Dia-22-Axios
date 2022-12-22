<template>
  <v-container>
    Hola
  </v-container>
</template>

<script>
import axios from "axios"

export default {
  data(){
    return{
      todos:null
    }
  },
  mounted(){
    axios.get('https://dummyjson.com/todos')
    .then(resposta=>{
      console.log(resposta)
      this.todos = resposta.todos
    })
    .catch(err=>{
      console.log(err)
    })
    /*
    .catch(function(err){
      console.log(err)
    })*/
  }
  
}
</script>
