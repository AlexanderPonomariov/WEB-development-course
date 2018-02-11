<template>
  <div id="app">
    <SearchForm />
    <!--<div v-for="(book, index) in books.items">{{book}}</div>-->

    <Books
      v-for="(book,index) in books.items"
      :book="book"
      :index="index"
      :key="book.id"
    />
  </div>
</template>

<script>

import Books from './components/Books';
import SearchForm from './components/SearchForm';

export default {
  name: 'app',
  data () {
    return {
      books: {},
    }
  },
  methods: {

  },
  components: {
    Books,
    SearchForm
  }
}
</script>
