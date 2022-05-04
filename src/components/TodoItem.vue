<template>

    <li
        @click="markTodo(p.id)"
        :class="p.check ? 'li_item_dark' : 'li_item_light'"
    >
      <my-input @click.stop type="text" v-model="p.text"/>
      <span
          @click="this.$emit('remove', p.id)"
          :class="!p.check ? 'span_dark' : 'span_light'"
      >
    X
    </span>
    </li>
</template>

<script>
import MyInput from "@/components/UI/MyInput";
export default {
  components: {MyInput},
  props: {
    p: {
      type: Object,
      required: true
    }
  },
  methods: {
    markTodo(id) {
        this.p.id === id && (this.p.check = !this.p.check)
    },

  }
}
</script>

<style scoped>
input {
  border-radius: 10px;
  padding: 10px;
  background-color: white;
  border: none;
  outline-color: royalblue;
}

li {
  position: relative;
}

.li_item_light {
  padding: 30px;
  background-color: aliceblue;
  width: 500px;
  margin: 15px;
}

.li_item_dark {
  padding: 30px;
  background-color: royalblue;
  width: 500px;
  margin: 15px;
}

.span_light {
  position: absolute;
  top: 0;
  right: 5px;
  cursor: pointer;
  color: aliceblue;
}

.span_dark {
  position: absolute;
  top: 0;
  right: 5px;
  cursor: pointer;
  color: royalblue;
}
</style>