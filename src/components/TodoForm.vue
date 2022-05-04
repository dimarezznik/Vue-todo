<template>
  <label>
    <my-input
        type="text"
        v-model="post.text"
    />
    <my-button @click="addTodo" >Add todo</my-button>
    <my-button @click="allMarkTodo">Mark all todo</my-button>
    <my-button @click="deleteMarkTodo" >
      Delete mark todo
    </my-button>
  </label>
</template>

<script>
import MyInput from "@/components/UI/MyInput";
import MyButton from "@/components/UI/MyButton";
export default {
  components: {
    MyButton,
    MyInput
  },
  data() {
    return {
      post: {
        text: '',
        check: false,
      }
    }
  },
  methods: {
    addTodo() {
      this.post.id = Date.now()
      this.$emit('add', this.post)
      this.post = {
        text: ''
      }
    },
    allMarkTodo() {
      this.$emit('markAll')
    },
    deleteMarkTodo() {
      this.$emit('deleteMark')
    }
  }
}
</script>

<style scoped>

label{
  background: aliceblue;
  padding: 50px;
  display: flex;
  justify-content: center;
  gap: 30px;
}

input{
  border-radius: 10px;
  padding: 10px;
  background-color: white;
  border: none;
  outline-color: royalblue;
}

</style>