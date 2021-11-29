<template>
<single-todo @delete="removeItem(todo)" @tick="checkDone(todo)" :todo="todo" v-for="todo in doneItems" :key="todo.id"></single-todo>
</template>

<script>
import SingleTodo from './SingleTodo.vue';
export default {
  components: { SingleTodo },
    props:{
        doneItems:{
            type: Array,
            required: true
        },
        uncompletedItems:{
            type: Array
        }
    }, 
    methods:{
        removeItem(todo){
      this.doneItems.splice(this.doneItems.indexOf(todo), 1);
    },
    checkDone(post){
         post.isDone = false;
         this.uncompletedItems.push(post);
         this.doneItems.splice(this.doneItems.indexOf(post), 1)
        }
    }
}
</script>

<style>

</style>