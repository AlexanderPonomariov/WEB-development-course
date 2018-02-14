<template>

  <div class="buy-pop-up" v-if="showAddedToCart || showOrder">

    <div class="pop-up" v-if="showAddedToCart">
      <div class="close" @click="closePopUp">X</div>
      <button class="send" @click="closePopUp">Continue shopping</button>
      <button class="send" @click="goToCart">Go to cart</button>
    </div>

    <div class="pop-up" v-if="showOrder">
      <div class="close" @click="closePopUp">X</div>
      <!--<img src="${bookNode.getElementsByClassName('book-image')[0].src}" alt="${bookNode.getElementsByClassName('book-image')[0].alt}" class="book-image">-->
      <!--<div class="book-description">${bookNode.getElementsByClassName('description')[0].innerText}</div>-->
      <div class="cart-item" v-for="cartItem in cart">
        <img :src="cartItem.volumeInfo.imageLinks.smallThumbnail" :alt="cartItem.volumeInfo.title" class="book-image" width="20%">
        <h4>{{cartItem.volumeInfo.title}}</h4>
        <div class="book-description">{{cartItem.volumeInfo.description}}</div>
      </div>

      <label><span>Name</span>
        <input type="text" name="name" required="required">
      </label>
      <label><span>e-mail</span>
        <input type="email" name="email" required="required">
      </label>
      <label><span>Phone number</span>
        <input type="text" name="phone-number" required="required">
      </label>
      <button class="send">Send</button>
    </div>
  </div>
</template>

<script>
    export default {
      name: "Cart",
      props: ['showAddedToCart','showOrder','cart'],
      data () {
        return {

        }
      },
      methods: {
        closePopUp() {
          this.$parent.showAddedToCart = false;
          this.$parent.showOrder = false;
        },
        goToCart() {
          this.$parent.showOrder = true;
        }
      }
    }
</script>
