<template>
  <div>
    <form v-on:submit.prevent='bookSubmit' class="" action="#" method="post">
      <input v-model='bookTitle' type="text" name="title" value="" placeholder="Book Title">
      <input v-model='bookAuthor' type="text" name="author" value="" placeholder="Book Author">
      <button type="submit" name="button">Add Book</button>
    </form>
  </div>
</template>

<script>
  export default {
    name: 'BookForm',
    data() {
      return {
        bookTitle: '',
        bookAuthor: ''
      }
    },
    methods: {
      bookSubmit() {
        this.$emit('addBook', this.bookTitle, this.bookAuthor);

        this.bookTitle = '';
        this.bookAuthor = '';
      }
    },
  }
</script>

<style scoped>

</style>
