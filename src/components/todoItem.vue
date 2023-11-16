<template>
  <p :class="['todo-item', todoProps.completed ? 'is-completed' : '']">
    <input type="checkbox" :checked="todoProps.completed" @change="mackItemCompleted" />
    {{ todoProps.title }}
    <button class="btn" @click="deleteItem">Delete</button>
  </p>
</template>

<script>
export default {
  name: 'todoItem',
  props: ['todoProps'],
  setup(props, context) {
    const mackItemCompleted = () => {
      context.emit('item-completed', props.todoProps.id);
    }
    const deleteItem = () => {
      context.emit('delete-item', props.todoProps.id);
    }
    return {
      mackItemCompleted,
      deleteItem
    }
  }
}
</script>

<style>
.todo-item {
  background: #f4f4f4;
  padding: 10px;
  margin: 0;
  border-bottom: 1px #ccc dotted;
}

.is-completed {
  text-decoration: line-through;
}

.btn {
  background: #ff0000;
  color: white;
  border: none;
  cursor: pointer;
  float: right;
}
</style>
