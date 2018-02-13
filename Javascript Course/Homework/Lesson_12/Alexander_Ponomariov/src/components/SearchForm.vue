<template>
  <div>
    <div class="cart">
      Goods in cart: {{cart.length}}
      <div class="cart-small">
        <div class="cart-item" v-for="cartItem in cart">
          <img :src="cartItem.volumeInfo.imageLinks.smallThumbnail" :alt="cartItem.volumeInfo.title" class="book-image">
          <h4>{{cartItem.volumeInfo.title}}</h4>
        </div>
      </div>
    </div>

    <form action="post" id="search-form">
      <label for="search-field">Set title or part of title</label>
      <input type="text" name="search-field" id="search-field">
      <input type="submit" value="search" @click="getBooks">
    </form>
  </div>
</template>

<script>
  export default {
    name: 'SearchForm',
    props: ['cart'],
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
        .then( books => this.$parent.books = books);
      }
    }
  }
</script>

