<template>
  <div class="blanc">
    <h1 class="title">Todo App</h1>
    <TodoInput />
    <TaskList v-bind:todos="todos" />
  </div>
</template>

<script>
import TodoInput from '@/components/TodoInput'
import TaskList from '@/components/TaskList'

export default {
  data () {
    return {
      todos: [
        { id: 1, task: 'Помыть посуду' },
        { id: 2, task: 'Помыть полы' },
        { id: 3, task: 'Купить хлеб' },
        { id: 4, task: 'Купить пива' }
      ]
    }
  },
  components: {
    TodoInput,
    TaskList
  }
}
</script>

<style scoped>
  .blanc {
    position: fixed;
    top: 50%;
    left: 50%;
    width: 380px;
    height: 500px;
    background: white;
    margin: -250px 0 0 -190px;
    border-radius: 10px;
  }

  .title {
    margin: 20px 0px 5px 25px;
  }
</style>
