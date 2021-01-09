<template>
  <div>
    <p v-if="products.length==0">The List is Empty</p>
    <table class="table" v-else>
      <thead>
        <tr>
          <th>#</th>
          <th>Product Name</th>
          <th>Category Id</th>
          <th>Description</th>
          <th>Unit Price</th>
          <th>Stock</th>
          <th></th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="product in products" :key="product.id">
            <td>{{product.id}}</td>
            <td>{{product.productName}}</td>
            <td>{{product.categoryId}}</td>
            <td>{{product.description}}</td>
            <td>{{product.unitPrice}}</td>
            <td>{{product.unitsInStock}}</td>
            <td><button class="btn btn-sm btn-danger" @click="handleDelete(product)">Delete</button></td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
    name:"product-list",
    props:{
      products:Array
    },
    methods:{
      handleDelete(product){
        this.$emit("delete:product",product)
      },
      handleUpdate(){

      }
    }
});
</script>

<style scoped></style>
