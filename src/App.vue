<template>
  <div class="main container my-3">
    <h1>Todo Application Vue 3</h1>
    <todo-form @addtodo="addTodo"></todo-form>
    <todo-list :todoItems="todos" @delete="removeItem"></todo-list>
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
        {id:1, title: 'Learn JavaScript', isDone: false},
        {id:2, title: 'Learn Vue.js', isDone: false}
      ]
    }
  },
  methods:{
    addTodo(todo){
      if (this.todos.length > 0) {
      todo.id = (this.todos[this.todos.length - 1].id) + 1
      } else {
        todo.id = 1;
        }
      todo.isDone = false
    this.todos.push(todo) 

    },
    removeItem(todo){
      this.todos.splice(this.todos.indexOf(todo), 1);
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
