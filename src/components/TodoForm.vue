<template>
  <div class="todoForm mb-5 row justify-content-center px-2">
<div v-if="isEmpty" class="col-md-8 alert alert-warning" role="alert">
        Todo field is required. Please type todo item
</div>

  <div class="col-sm-12 col-md-10 mb-2">
  <input type="email" 
  class="form-control" 
  placeholder="Learn Vue.js"
  v-model="todo.title"
  @keyup.enter="addTodoitem"
  @input="isEmpty=false">
  </div>
  <div class="col-md-2 d-flex mb-2 justify-content-end">
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