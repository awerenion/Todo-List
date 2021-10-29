<template>
  <div>
    <button class="btn" @click="$emit('click')">Clear All</button>
  </div>
</template>

<script>
</script>

<style scope>
  .btn {
    width: 90px;
    height: 30px;
    color: white;
    background: #24c6dc;
    border: none;
    border-radius: 2px;
    cursor: pointer;
    letter-spacing: 1px;
  }
</style>
