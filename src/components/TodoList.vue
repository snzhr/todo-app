<template>
  <div class="card d-flex flex-row align-items-center mb-2" v-for="todo in todoItems" :key="todo.id">
  <div class="card-body">
   <span class="card-title">{{todo.title}}</span>
  </div>
  <button type="button" @click="$emit('delete', todo)" class="btn-close mx-3" aria-label="Close"></button>
</div>
</template>

<script>
export default {
    props:{
        todoItems:{
            type: Array,
            required: true
        }
    }
}
</script>

<style>

</style>