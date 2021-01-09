<template>
  <div class="product-add">
    <form class="form" @submit.prevent="handleAdd"> 
      <div class="form-group">
        <label for="categoryId">Category Id</label>
        <input
          v-model="product.categoryId"
          type="text"
          class="form-control"
          id="categoryId"
        />
      </div>
      <div class="form-group">
        <label for="productName">Product Name</label>
        <input
          v-model="product.productName"
          type="text"
          class="form-control"
          id="productName"
        />
      </div>
      <div class="form-group">
        <label for="quentityPerUnit">Description</label>
        <input
          v-model="product.quentityPerUnit"
          type="text"
          class="form-control"
          id="quentityPerUnit"
        />
      </div>
      <div class="form-group">
        <label for="unitPrice">Unit Price</label>
        <input
          v-model="product.unitPrice"
          type="text"
          class="form-control"
          id="unitPrice"
        />
      </div>
      <div class="form-group">
        <label for="unitsInStock">Units In Stock</label>
        <input
          v-model="product.unitsInStock"
          type="text"
          class="form-control"
          id="unitsInStock"
        />
      </div>
      <button type="submit" class="btn btn-sm btn-primary" > Add Product</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "product-add",
  data() {
    return {
      product: {
        categoryId: "",
        productName: "",
        quentityPerUnit: "",
        unitPrice: "",
        unitsInStock: "",
      },
    };
  },
  methods:{
      handleAdd(){
          this.$emit("add:product",this.product)
      }
  }
};
</script>

<style scoped>
.product-add {
  margin: 10px 200px;
}
</style>
