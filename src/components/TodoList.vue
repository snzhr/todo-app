<template>
<div>
<single-todo @delete="removeItem" @tick="checkDone(todo)" :todo="todo" v-for="todo in todoItems" :key="todo.id"></single-todo>
</div>
</template>

<script>
import SingleTodo from './SingleTodo.vue';
export default {
  components: { SingleTodo },
    props:{
        todoItems:{
            type: Array,
            required: true
        },
        completedTodos:{
            type: Array
        }
    }, 
    methods:{
        removeItem(todo){
      this.todoItems.splice(this.todoItems.indexOf(todo), 1);
    },
     checkDone(post){
         post.isDone = true;
         this.completedTodos.push(post);
         this.todoItems.splice(this.todoItems.indexOf(post), 1)
        }
    }
}
</script>
