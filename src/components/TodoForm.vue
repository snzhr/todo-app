<template>
  <div class="todoForm mb-5 row justify-content-center">

<div v-if="isEmpty" class="col-10 alert alert-warning" role="alert">
        Todo field is required. Please type todo item
</div>

  <div :id="isEmpty" class="col-8">
  <input type="email" 
  class="form-control" 
  id="exampleFormControlInput1" 
  placeholder="Learn Vue.js"
  v-model="todo.title"
  @keyup.enter="addTodoitem"
  @input="isEmpty=false">
  </div>
  <div class="col-2 d-flex justify-content-end">
  <button type="button" @click="addTodoitem" class="btn btn-primary">Add Todo</button>
  </div>
</div>


</template>

<script>
export default {
  data(){
    return{
      todo:{
          title:''
      },
      isEmpty : false
    }
  },
  methods:{
  addTodoitem(){
  if (this.todo.title == '') {
      this.isEmpty = true
    }
    else{
      this.$emit('addtodo', this.todo)
      this.todo = {
        title: ''
      }
    } 
  
  }
  
  
  }
}
</script>

<style>
</style>