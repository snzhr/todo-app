<template>
  <div class="main container my-3">
    <h1>Todo Application</h1>
    <todo-form @addtodo="addTodo"></todo-form>
    <todo-list :todoItems="todos"></todo-list>
  </div>
</template>

<script>
import TodoForm from "./components/TodoForm.vue";
import TodoList from './components/TodoList.vue'
export default {
  name: "App",
  components: {
    TodoForm, TodoList
  },
  data(){
    return{
      todos:[
        { title: 'Learn Vue.js'},
        {title: 'Learn Node.js'}
      ]
    }
  },
  methods:{
    addTodo(todo){
      this.todos.push(todo)
    }
  }
};
</script>

<style>
.main {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
.main h1{
  text-align: center;
}
</style>
