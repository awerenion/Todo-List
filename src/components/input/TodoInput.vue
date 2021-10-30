<template>
  <div class="container">
    <input
      type="text"
      class="inputTodo"
      id="input"
      @focus="togglePlaceholder"
      @blur="togglePlaceholder"
      v-model="inputValue"
      @keyup.enter="addNewTask"
    >
    <label
      for="input"
      class="placeholder"
      v-show="isPlaceholderShow && !inputValue.length"
    >
      Add your new todo
    </label>
    <add-button
      @click="addNewTask"
    />
  </div>
</template>

<script>
import AddButton from '@/components/input/AddButton'

export default {
  name: 'TodoInput',
  data () {
    return {
      inputValue: '',
      isPlaceholderShow: true
    }
  },
  components: {
    AddButton
  },
  methods: {
    togglePlaceholder () {
      this.isPlaceholderShow = !this.isPlaceholderShow
    },
    addNewTask () {
      if (this.inputValue.length) {
        this.$emit('new', this.inputValue)
      }
      this.inputValue = ''
    }
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
    font-weight: 400;
  }

  .container {
    display: flex;
    position: relative;
  }

  .placeholder {
    position: absolute;
    opacity: 0.8;
    top: calc(60% - 15px);
    left: calc(9% + 2px);
    font-size: 16px;
    cursor: text;
  }

</style>
