<template>
  <div class='ui basic content center aligned segment'>
    <button class='ui basic button icon' @click="sortTodos">
      <i v-if="desc" class="sort descending icon"></i>
      <i v-else class="sort ascending icon"></i>
    </button>
  </div>
</template>

<script>
export default {
  props: ['desc'],
  methods: {
    sortTodos (dir) {
      this.$emit('sort-todos', dir)
    }
  }
}
</script>

<style></style>
