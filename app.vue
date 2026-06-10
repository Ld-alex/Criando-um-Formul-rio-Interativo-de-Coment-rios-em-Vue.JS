<template>
  <div class="container">
    <h1>Sistema de Comentários</h1>

    <CommentForm @add-comment="addComment" />

    <CommentList :comments="comments" />
  </div>
</template>

<script>
import CommentForm from './components/CommentForm.vue'
import CommentList from './components/CommentList.vue'

export default {
  components: {
    CommentForm,
    CommentList
  },

  data() {
    return {
      comments: []
    }
  },

  methods: {
    addComment(comment) {
      this.comments.push(comment)
    }
  }
}
</script>

<style>
.container {
  width: 600px;
  margin: auto;
  font-family: Arial, sans-serif;
}
</style>