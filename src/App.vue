<template>
<div>
  <todo-form @add="addPost" @markAll="allMarkTodo" @deleteMark="deleteMarkTodo" />
  <todo-list :posts="posts" @remove="removeTodo" />
</div>
</template>

<script>
import TodoForm from "@/components/TodoForm";
import TodoList from "@/components/TodoList";
export default {
  name: 'App',
  components: {
    TodoForm, TodoList
  },
  data() {
    return {
      posts: []
    }
  },
  methods: {
    addPost(post) {
      if (!post.text.trim()) return;
      this.posts.push(post)
    },
    allMarkTodo() {
      this.posts.forEach(post => {
        post.check = true
      })
    },
    deleteMarkTodo() {
      this.posts = this.posts.filter(post => post.check !== true)
    },
    removeTodo(id) {
      this.posts = this.posts.filter(post => post.id !== id)
    }
  }

}

</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body{
  height: 100vh;
  background-color: #E5E5E5;
}
</style>
