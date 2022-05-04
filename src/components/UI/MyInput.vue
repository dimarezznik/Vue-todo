<template>
    <input
        type="text"
        class="inp_form"
        :value="modelValue"
        @input="updateInput"
    />
</template>

<script>
export default {
  props: {
    modelValue: {
      type: [String, Number]
    }
  },
  methods: {
    updateInput(e) {
      this.$emit('update:modelValue', e.target.value)
    }
  }
}
</script>

<style scoped>
input{
  border-radius: 10px;
  padding: 10px;
  background-color: white;
  border: none;
  outline-color: royalblue;
}
</style>