<template>
  <div id="app">
    <ProductList @delete:product="deleteProduct" @update:product="updateProduct" :products="products"/>
    <ProductAdd @add:product="addProduct" />
  </div>
</template>

<script>
import ProductList from "./components/ProductList.vue";
import ProductAdd from "./components/ProductAdd.vue";

export default {
  name: "App",
  components: {
    ProductList,
    ProductAdd
  },
  data() {
    return {
      products: [
        {
          id: 1,
          categoryId: 1,
          productName: "Classical Guitar",
          description: "Cordoba Guitar",
          unitPrice: 375,
          unitsInStock: 2,
        },
        {
          id: 2,
          categoryId: 3,
          productName: "Drum Set",
          description: "Yamaha",
          unitPrice: 375,
          unitsInStock: 2,
        },
        {
          id: 3,
          categoryId:1,
          productName: "Acoustic Guitar",
          description: "Yamaha Guitar",
          unitPrice: 450,
          unitsInStock: 3,
        },
        {
          id: 4,
          categoryId: 2,
          productName: "Piano",
          description: "Pearl River Piano",
          unitPrice: 8765,
          unitsInStock: 1,
        },
      ],
    };
  },
  methods:{
    deleteProduct(product){
      this.products = this.products.filter(
        productToFilter => productToFilter.id !== product.id
      )
    },
    updateProduct(product){
      product;
    },
    addProduct(product){
      const newProduct = {...product};
      this.products = [...this.products,newProduct];
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
