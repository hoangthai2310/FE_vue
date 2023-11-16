<template>
  <div>
    <AddTodo/>
    <todoItem
      v-for="todo in todos"
      :key="todo.id"
      :todoProps="todo"
      @item-completed="mackComple"
      @delete-item="deleteComplete"
    />
  </div>
</template>

<script>
import { ref } from 'vue'
import AddTodo from './addTodo.vue'
import todoItem from './todoItem.vue'

export default {
  name: 'TodosList',
  components: { todoItem , AddTodo },
  setup() {
    const todos = ref([
      {
        id: 1,
        title: 'viec 1',
        completed: false
      },
      {
        id: 2,
        title: 'viec 2',
        completed: false
      },
      {
        id: 3,
        title: 'viec 3',
        completed: false
      }
    ])

    const mackComple = id => {
      todos.value = todos.value.map(todo => {
        if (todo.id === id) todo.completed = !todo.completed
        return todo
      })
    }
    const deleteComplete = id =>{
       todos.value = todos.value.filter(todo => todo.id !== id)
    }

    return {
      todos,
      mackComple,
      deleteComplete
    }
  }
}
</script>

<style>
</style>
