<template>
  <ul>
    <todo-item v-for="p in posts"
               :key="p.id"
               :p="p" @remove="this.$emit('remove', p.id)" />
  </ul>
</template>

<script>
import TodoItem from "@/components/TodoItem";

export default {
  components: {
    TodoItem
  },
  props: {
    posts: {
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>


ul {
  display: flex;
  align-items: center;
  flex-direction: column;
  list-style: none;
}


</style>