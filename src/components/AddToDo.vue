<template>
    <div class="input_elem">
      <input v-model="newTodo" @keyup.enter="addTodo"/>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        newTodo: '' 
      }
    },
    methods: {
      addTodo() {
          this.$emit('addNewTodo', this.newTodo)
          this.newTodo = ''
      }
    }
  }
  </script>
  
  