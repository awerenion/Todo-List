<template>
  <div
    @click="$emit('click')"
  >
    <button class="addTodo">
      <img src="@/assets/ftedit-add.svg" class="img">
    </button>
  </div>
</template>

<script>
export default {
  name: 'AddButton'
}
</script>

<style scoped>
  .addTodo {
    width: 45px;
    height: 40px;
    margin: 20px 0px 0px 15px;
    background: #24c6dc;
    border: 1px solid #24c6dc;
    border-radius: 2px;
    cursor: pointer;
  }

  .img {
    padding-top: 3px;
    height: 20px;
    width: 20px;
    color: white;
  }

</style>
