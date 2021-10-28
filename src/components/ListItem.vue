<template>
  <div>
    {{ todo.task }}
  </div>
</template>

<script>
export default {
  props: {
    todo: {
      Object: true,
      required: true
    }
  }
}
</script>
