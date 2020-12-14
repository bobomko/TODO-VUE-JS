<template>
  <div v-bind:class="{ 'is-complete': todo.completed }">
    <p class="todo-item">
      <input type="checkbox" v-on:change="markComplete" />
      {{ todo.title }}
      <button @click="$emit('del-todo', todo.id)" class="del">X</button>
    </p>
  </div>
</template>

<script>
export default {
  name: 'TodoItem',
  props: ['todo'],
  methods: {
    markComplete() {
      console.log(123)
      this.todo.completed = !this.todo.completed
    },
  },
}
</script>

<style scoped>
.todo-item {
  display: flex;
  justify-content: space-between;
  background: #f4f4f4;
  margin: 10px 1em;
  padding: 1em 5em;
  border-bottom: 1px #ccc dotted;
}
.is-complete {
  text-decoration: line-through;
  background: #affe11;
}
.del {
  background: #ff0000;
  color: #fff;
  border: none;
  padding: 5px 9px;
  border-radius: 50%;
  cursor: pointer;
}
</style>
