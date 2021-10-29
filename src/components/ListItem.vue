<template>
  <div @mouseover="isHovered=true" @mouseleave="isHovered=false">
    <span>{{ todo.task }}</span>
    <transition name="fade">
      <button class="remove_button" v-show="isHovered" @click="removeTask">
        <img src="@/assets/trash.svg" alt="remove" class="img">
      </button>
    </transition>
  </div>
</template>

<script>
export default {
  data () {
    return {
      isHovered: false
    }
  },
  props: {
    todo: {
      type: Object,
      required: true
    }
  },
  methods: {
    removeTask () {
      this.$emit('remove', this.todo.id)
    }
  }
}
</script>

<style scoped>
  .remove_button {
    display: flex;
    align-items: center;
    justify-content: center;
    position: absolute;
    right: 1px;
    width: 45px;
    height: 100%;
    background: #E64D3F;
    border: none;
    border-radius: 0px 4px 4px 0px;
    z-index: 1;
    cursor: pointer;
  }

  .img {
    width: 65%;
    height: 65%;
    z-index: 99;
  }

.fade-enter-active, .fade-leave-active {
  transition: opacity .5s;
}
.fade-enter, .fade-leave-to {
  opacity: 0;
}
</style>
