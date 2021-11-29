<template>
  <div class="card d-flex flex-row align-items-center mb-2" v-for="todo in todoItems" :key="todo.id">
  <input class="form-check-input mx-3 mb-1" type="checkbox" @change="checkDone(todo)">
  <div class="card-body">
   <span class="card-title" :class="{doneItem:todo.isDone}" :data-status="todo.isDone">{{todo.title}}</span>
  </div>
  <button type="button" @click="$emit('delete', todo)" class="btn-close bg-danger mx-3" aria-label="Close"></button>
</div>
</template>

<script>
export default {
    props:{
        todoItems:{
            type: Array,
            required: true
        }
    },
    methods:{
        checkDone(post){
           if (post.isDone === false) {
           post.isDone = true;
           } else {
           post.isDone = false;
           }
        }
    }  
}
</script>

<style>
.doneItem{
    text-decoration: line-through;
}
.form-check-input{
    cursor: pointer;
}
</style>