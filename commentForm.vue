<template>
  <form @submit.prevent="submitComment">
    <div>
      <label>Nome:</label>
      <input
        type="text"
        v-model="name"
        required
      />
    </div>

    <div>
      <label>Comentário:</label>
      <textarea
        v-model="text"
        required
      ></textarea>
    </div>

    <button type="submit">
      Adicionar Comentário
    </button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      name: '',
      text: ''
    }
  },

  methods: {
    submitComment() {
      this.$emit('add-comment', {
        name: this.name,
        text: this.text
      })

      this.name = ''
      this.text = ''
    }
  }
}
</script>

<style scoped>
form {
  margin-bottom: 20px;
}

input,
textarea {
  width: 100%;
  margin-top: 5px;
  margin-bottom: 10px;
  padding: 8px;
}

button {
  padding: 8px 15px;
}
</style>