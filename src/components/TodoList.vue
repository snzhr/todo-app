<template>
  <div class="card mb-2" v-for="todo in todoItems" :key="todo.id">
  <div class="card-body">
   <h6 class="card-title">{{todo.title}}</h6>
  </div>
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