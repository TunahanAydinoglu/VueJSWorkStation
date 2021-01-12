<template>
    <div class="input-container">
      <input type="text" v-model="productID">
      <button class="button--green" @click="showProduct"> Show Product</button>
    </div>
</template>

<script>
export default {
   data(){
      return {
        productID : null
      }
    },
    methods : {
      showProduct(){
        this.$router.push("/products/" + this.productID)
  }
      }
}
</script>

<style>
  .input-container{
    padding: 20px;
    border: 1px solid #688fb9;
    background-color: #35495e;
    box-shadow: 2px 3px 8px rgba(0,0,0,.1);
    text-align: center;
  }
  input{
    border: none;
    outline: none;
    height: 30px;
    font-size: 18px;
    color: #35495e;
  }
</style>