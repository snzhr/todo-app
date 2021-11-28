<template>
  <div class="todoForm mb-5 row justify-content-center">
  <div class="col-8">
  <input type="email" 
  class="form-control" 
  id="exampleFormControlInput1" 
  placeholder="Learn Vue.js"
  v-model="todo.title"
  @keyup.enter="addTodoitem">
  </div>
  <div class="col-2">
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
      }
    }
  },
  methods:{
    addTodoitem(){
      this.$emit('addtodo', this.todo)
      this.todo = {
        title: ''
      }
    }
  }
}
</script>

<style>

</style>