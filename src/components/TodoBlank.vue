<template>
  <div class="blanc">
    <h1 class="title">Todo App</h1>
    <todo-input
      @new="addNewTodoTask"
    />
    <task-list
      :todos="todos"
      @remove="removeTask"
    />

    <div class="footer">
      <span class="text">You have {{ this.todos.length }} pending tasks</span>
      <clear-tasks
        class="btn"
        @click="clearAll"
      ></clear-tasks>
    </div>
  </div>
</template>

<script>
import TodoInput from '@/components/input/TodoInput'
import TaskList from '@/components/tasks/TaskList'
import ClearTasks from '@/components/tasks/ClearTasks'

export default {
  data () {
    return {
      todos: [
      ]
    }
  },
  components: {
    TodoInput,
    TaskList,
    ClearTasks
  },
  methods: {
    removeTask (id) {
      this.todos = this.todos.filter(todo => todo.id !== id)
    },
    addNewTodoTask (taskText) {
      if (!this.todos.length) {
        this.todos.push({
          id: 1,
          task: taskText
        })
      } else {
        const lastId = this.todos.sort((a, b) => a.id - b.id)[this.todos.length - 1].id
        this.todos.push({
          id: lastId + 1,
          task: taskText
        })
      }
    },
    clearAll () {
      this.todos.splice(0, this.todos.length)
    }
  }
}
</script>

<style scoped>
  .blanc {
    position: fixed;
    top: 50%;
    left: 50%;
    width: 380px;
    background: white;
    margin: -250px 0 0 -190px;
    border-radius: 10px;
  }

  .title {
    margin: 20px 0px 5px 25px;
  }

  .footer {
    width: 100%;
    display: flex;
    justify-content: space-around;
    align-items: center;
    margin-bottom: 15px;
  }

  .btn {
    margin-left: 38px;
  }

  .text {
    font-weight: 400;
    font-style: italic;
  }
</style>
