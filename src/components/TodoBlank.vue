<template>
  <div class="blanc">
    <h1 class="title">Todo App</h1>
    <TodoInput />
  </div>
</template>

<script>
import TodoInput from '@/components/TodoInput'

export default {
  components: {
    TodoInput
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
