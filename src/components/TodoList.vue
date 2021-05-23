<template>
  <div>
    <ul>
      <TodoItem
          v-for="(todo, index) in todos"
          :todo="todo"
          :index="index"
          v-on:remove-todo="removeTodo"
      />
    </ul>
  </div>
</template>

<script>
import TodoItem from "./TodoItem";
export default {
  name: "TodoList",
  props: ['todos'],
  components:{
    TodoItem
  },
  methods:{
    removeTodo(id) {
      this.$emit('remove-todo', id)
    }
  }
}
</script>

<style scoped>

</style>