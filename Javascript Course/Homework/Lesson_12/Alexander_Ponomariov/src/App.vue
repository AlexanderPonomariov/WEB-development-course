<template>
  <div id="app">
    <SearchForm
      :cart="cart"
    />
    <!--<div v-for="(book, index) in books.items">{{book}}</div>-->

    <Books
      v-for="(book,index) in books.items"
      :book="book"
      :index="index"
      :key="book.id"
    />

    <Cart
      :showAddedToCart="showAddedToCart"
      :showOrder="showOrder"
      :cart="cart"
    />

  </div>
</template>

<script>

import Books from './components/Books';
import SearchForm from './components/SearchForm';
import Cart from './components/Cart';

export default {
  name: 'app',
  data () {
    return {
      books: {},
      cart: [],
      showAddedToCart: false,
      showOrder: false,
    }
  },
  methods: {

  },
  components: {
    Books,
    SearchForm,
    Cart
  }
}
</script>
