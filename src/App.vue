<template>
  <div class="main container my-3">
    <h1>Todo Application Vue 3</h1>
    <todo-form @addtodo="addTodo"></todo-form>
    <div class="row">
        <div class="col-6">
          <h4>Todo tasks</h4>
    <todo-list :todoItems="todos" :completedTodos="doneTodos"></todo-list>
        </div>
        <div class="col-6">
          <h4>Completed tasks</h4>
          <done-list :doneItems="doneTodos" :uncompletedItems="todos"></done-list>
        </div>
    </div>
  </div>
</template>

<script>
import TodoForm from "./components/TodoForm.vue";
import TodoList from './components/TodoList.vue'
import DoneList from "./components/DoneList.vue"
export default {
  name: "App",
  components: {
    TodoForm, TodoList, DoneList
  },
  data(){
    return{
      todos:[
        {id:1, title: 'Learn JavaScript', isDone: false},
        {id:2, title: 'Learn Vue.js', isDone: false}
      ],
      doneTodos:[{id:1, title: 'Learn HTML', isDone: true}]
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
