<template>

  <div class="buy-pop-up">

    <div class="pop-up">
      <div class="close" @click="closePopUp">X</div>
      <!--<img src="${bookNode.getElementsByClassName('book-image')[0].src}" alt="${bookNode.getElementsByClassName('book-image')[0].alt}" class="book-image">-->
      <!--<div class="book-description">${bookNode.getElementsByClassName('description')[0].innerText}</div>-->
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
      props: ['cart'],
      data () {
        return {

        }
      },
      methods: {
        closePopUp(){
          this.$parent.showAddedToCart = false;
        }
      }
    }
</script>
