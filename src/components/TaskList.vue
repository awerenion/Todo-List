<template>
  <div>
    <ul>
      <ListItem
      v-for="todo of todos"
      v-bind:todo="todo"
      v-bind:key="todo"/>
    </ul>
  </div>
</template>

<script>
import ListItem from '@/components/ListItem'

export default {
  props: ['todos'],
  components: {
    ListItem
  }

}
</script>

<style scoped>
</style>
