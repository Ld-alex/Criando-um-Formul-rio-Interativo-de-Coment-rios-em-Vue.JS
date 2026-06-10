<template>
  <div>
    <h2>Comentários</h2>

    <div
      v-if="comments.length === 0"
    >
      Nenhum comentário ainda.
    </div>

    <div
      v-for="(comment, index) in comments"
      :key="index"
      class="comment"
    >
      <h3>{{ comment.name }}</h3>
      <p>{{ comment.text }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    comments: Array
  }
}
</script>

<style scoped>
.comment {
  border: 1px solid #ccc;
  padding: 10px;
  margin-bottom: 10px;
}
</style>