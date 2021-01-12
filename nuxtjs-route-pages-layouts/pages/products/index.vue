<template>
  <div class="container">
    <h2>Products Page</h2>
    <div class="input-container">
      <input type="text" v-model="productId" />
      <button class="button--green" @click="showProduct">Show Product</button>
    </div>
  </div>
</template>

<script>
export default {
    data(){
    return{
      productId:null
    }
  },
  methods:{
    showProduct(){
      this.$router.push("/products/"+this.productId)
    }
  }
};
</script>

<style></style>
