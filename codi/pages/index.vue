<template>
  <v-container>
    <v-row>
      <v-col cols="12" v-for="todo in todos" >
        <div>{{ todo.todo }}</div>
        <div v-if="todo.completed" >feta</div>
        <div v-else>per fer</div>
        <div>{{ todo.userId }}</div>
      </v-col>
    </v-row>
    Hola
  </v-container>
</template>

<script>
import axios from "axios"

export default {
  data(){
    return{
      todos:null,
      total:0
    }
  },
  mounted(){
    this.descarregarTodos()
    this.descarregarUsuaris()
  },
  methods:{
    descarregarTodos(){
      axios.get('https://dummyjson.com/todos')
      .then(resposta=>{
      console.log(resposta)
    })
    .catch(err=>{
      console.log(err)
    })
  }
    /*
    .catch(function(err){
      console.log(err)
    })*/
    },
    descarregarUsuaris(){
      axios.get('https://dummyjson.com/users')
      .then(resposta=>{
       console.log(resposta)
      })
      .catch(err=>{
        console.log(err) 
      })
    }
  }
</script>
