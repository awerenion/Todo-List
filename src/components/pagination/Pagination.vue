<template>
  <div
    class="pagination"
    v-show="isPaginationShow"
  >
    <div
      v-for="page in pagesCount"
      :key="page"
    >
      <span
        class="page"
        :class="{'active-page': isCurrentPage(page)}"
        @click="changePage(page)"
      >
        {{ page }}
      </span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Pagination',
  props: {
    todos: {
      type: Array,
      required: true
    },
    currentPage: {
      type: Number,
      required: true
    },
    taskToPage: {
      type: Number,
      required: true
    }
  },
  computed: {
    pagesCount () {
      return Math.ceil(this.todos.length / this.taskToPage)
    },
    isPaginationShow () {
      return this.pagesCount > 1
    }
  },
  methods: {
    changePage (page) {
      this.$emit('change', page)
    },
    isCurrentPage (page) {
      return page === this.currentPage
    }
  }
}
</script>

<style scoped>
  .pagination {
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .page {
    margin-right: 5px;
    cursor: pointer;
  }

  .active-page {
    font-weight: bold;
  }
</style>
