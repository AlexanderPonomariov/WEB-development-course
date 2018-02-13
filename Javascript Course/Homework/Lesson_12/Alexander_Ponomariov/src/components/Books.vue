<template>
  <div class="book-block">
    <img :src="book.volumeInfo.imageLinks.smallThumbnail" :alt="book.volumeInfo.title" class="book-image">
    <h2>{{book.volumeInfo.title}}</h2>
    <div class="authors">Author{{ book.volumeInfo.authors && book.volumeInfo.authors.length > 1 ? 's' : '' }}: {{book.volumeInfo.authors ? book.volumeInfo.authors.join(', ') : 'no information' }}</div>
    <div class="pub-date">Published date: {{new Date(book.volumeInfo.publishedDate).toLocaleDateString()}}</div>
    <div class="description">Description: {{book.volumeInfo.description ? book.volumeInfo.description : 'no infiormation'}}</div>

    <button class="buy-button" @click="showAddedToCart(),addToCart()">Buy</button>
  </div>

</template>

<script>
  export default {
    name: 'Books',
    props: ["book","index"],
    data () {
      return {

      }
    },
    methods: {
      showAddedToCart(){
        this.$parent.showAddedToCart = true;
      },
      addToCart(){
        console.log(this.book);
        this.$parent.cart.push(this.book);
      }
    }
  }
</script>

