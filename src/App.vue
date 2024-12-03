<script>
import AddToDo from './components/AddToDo.vue'
import ToDoList from './components/ToDoList.vue'

export default {
  components: {AddToDo, ToDoList},
  data(){
    return {
          data: [
            {id: 1, title: 'Позавтракать', completed: true},
            {id: 2, title: 'Почистить огурцы', completed: false},
            {id: 3, title: 'Помыть кота', completed: true},
          ]
    }
  },
  methods: {
    removeTodo(id){
      this.data = this.data.filter((elem => elem.id !== id))
    },
    changeTodo(id){
      this.data = this.data.map(elem => {
      if (elem.id === id){
        elem.completed = !elem.completed
      }
      return elem
    })
    },
    addNewTodo(title){
      const newTodo = {
      id: Date.now(),
      completed: false,
      title
    }
    this.data.push(newTodo)
    }
  }
}
</script>

<template>
 <add-to-do
 @addNewTodo="addNewTodo">

 </add-to-do>


 <to-do-list 
  :data="data"
  @removeTodo="removeTodo"
  @changeTodo="changeTodo">

 </to-do-list>

</template>

<style>
  .todo_item{
      display: flex;
      flex-direction: column;

      margin: 20px 170px;
      padding: 10px;

      outline: 2px solid black;
      box-shadow: 5px 5px 5px black;
  }


  .input_elem{
      display: flex;
      justify-content: center;
      margin: 20px 400px;
  }

  .input_elem > input{
      width: 100%;
      box-shadow: 5px 5px 5px black;
  }
</style>
