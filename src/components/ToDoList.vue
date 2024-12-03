<template>
    <div v-for="(elem, index) in data" 
        :key="index">
        <to-do-item 
        :id="elem.id" 
        :title="elem.title" 
        :completed="elem.completed"
        @removeTodo="$emit('removeTodo', elem.id)" 
        @changeTodo="$emit('changeTodo', elem.id)">
    </to-do-item>
    </div>
  </template>
  


<script>
import ToDoItem from './ToDoItem.vue'
    export default {
        props: {
            data: Array
        },
        components: {ToDoItem}
    }
</script>
