<template>
  <button >
    <slot></slot>
  </button>
</template>

<script>
export default {

}
</script>

<style scoped>
button{
  background-color: royalblue;
  padding: 10px;
  border-radius: 10px;
  border: none;
  color: white;
  cursor: pointer;
}
</style>