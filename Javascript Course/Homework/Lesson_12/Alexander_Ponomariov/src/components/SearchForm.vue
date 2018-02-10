<template>
  <form action="post" id="search-form">
    <label for="search-field">Set title or part of title</label>
    <input type="text" name="search-field" id="search-field">
    <input type="submit" value="search" @click="getBooks">
  </form>
</template>

<script>
  export default {
    name: 'SearchForm',
    data () {
      return {
        books: {},
      }
    },
    methods: {
      getBooks(e) {
        e.preventDefault()
        fetch(
          'https://www.googleapis.com/books/v1/volumes?q=harry',
          {method:'get'},)
        .then( response => response.json())
        .then( books => {
          this.$parent.books = books;
        });
      }
    }
  }
</script>

