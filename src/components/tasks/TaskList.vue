<template>
  <div>
    <ul>
      <list-item
        class="task_item"
        v-for="todo of todos"
        :todo="todo"
        :key="todo.id"
        @remove="removeTask"
      />
    </ul>
  </div>
</template>

<script>
import ListItem from '@/components/tasks/ListItem'

export default {
  name: 'TaskList',
  data () {
    return {
      pageNumber: 0
    }
  },
  props: {
    todos: {
      type: Array,
      required: true
    }
  },
  components: {
    ListItem
  },
  methods: {
    removeTask (id) {
      this.$emit('remove', id)
    }
  }
}
</script>

<style scoped>
.task_item {
  display: flex;
  align-items: center;
  position: relative;
  width: 309px;
  background: #f2f3f4;
  margin: 10px 0px 10px -15px;
  padding: 12px 12px;
  border-radius: 0px 4px 4px 0px;
}
</style>
