<template>
  <div id="app">
    <SearchForm />
    <div>{{books}}</div>

    <!--<Books-->
    <!--v-for="(book, index) in books"-->
    <!--/>-->
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
