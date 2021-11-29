<template>
   <div class="card d-flex flex-row align-items-center mb-2">
  <input class="form-check-input mx-3 mb-1" type="checkbox" :checked="todo.isDone" @change="$emit('tick', todo)">
  <div class="card-body">
   <span class="card-title" :class="{doneItem:todo.isDone}" :data-status="todo.isDone">{{todo.title}}</span>
  </div>
  <button type="button" @click="$emit('delete', todo)" class="btn-close close-custom mx-3" aria-label="Close"></button>
   
</div>
</template>

<script>
export default {
    props:{
        todo:{
            type: Object
        }
    },
      
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