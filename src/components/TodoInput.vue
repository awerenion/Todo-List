<template>
  <div class="container">
    <input type="text" placeholder="Add your new todo" class="inputTodo">
    <AddButton />
  </div>
</template>

<script>
import AddButton from '@/components/AddButton'

export default {
  components: {
    AddButton
  }
}
</script>

<style scoped>
  .inputTodo {
    margin: 20px 0px 15px 25px;
    font-size: 16px;
    padding: 10px;
    display: block;
    width: 250px;
    border: 1px solid #ccc;
    border-radius: 2px;
  }

  .container {
    display: flex;
  }
</style>
