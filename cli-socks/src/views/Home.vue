<template>
  <div>
    <Product :premium="premium" @add-to-cart="updateCart" @remove-from-cart="removeFromCart" :cartLength="cart.length"></Product>

    <div class="cart">
      {{ cart.length }}
      <i class="fas fa-shopping-cart"></i>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Product from "../components/Product.vue";

@Component({
  components: {
    Product
  }
})
export default class Home extends Vue {
  premium = true;
  cart: string[] = [];

  updateCart(product: any) {
    console.log("Adding to cart:", product);
    this.cart.push(product);
  }

  removeFromCart(product: any) {
    let index = this.cart.indexOf(product);
    this.cart.splice(index);
  }
}
</script>
