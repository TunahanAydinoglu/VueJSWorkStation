<template>
  <div class="product-list">
    <p v-if="products.length == 0">The List is Empty</p>
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
          <td v-if="product.id === updateItemId">
            <input
              v-model="product.id"
              type="text"
              class="form-control"
              id="id"
            />
          </td>
          <td v-else>{{ product.id }}</td>

          <td v-if="product.id === updateItemId">
            <input
              v-model="product.productName"
              type="text"
              class="form-control"
              id="productName"
            />
          </td>
          <td v-else>{{ product.productName }}</td>

          <td v-if="product.id === updateItemId">
            <input
              v-model="product.categoryId"
              type="text"
              class="form-control"
              id="categoryId"
            />
          </td>
          <td v-else>{{ product.categoryId }}</td>

          <td v-if="product.id === updateItemId">
            <input
              v-model="product.description"
              type="text"
              class="form-control"
              id="description"
            />
          </td>
          <td v-else>{{ product.description }}</td>

          <td v-if="product.id === updateItemId">
            <input
              v-model="product.unitPrice"
              type="text"
              class="form-control"
              id="unitPrice"
            />
          </td>
          <td v-else>{{ product.unitPrice }}</td>

          <td v-if="product.id === updateItemId">
            <input
              v-model="product.unitsInStock"
              type="text"
              class="form-control"
              id="unitsInStock"
            />
          </td>
          <td v-else>{{ product.unitsInStock }}</td>

          <td v-if="updateItemId !== product.id">
            <button
              class="btn btn-sm btn-success"
              @click="handleUpdate(product)"
            >
              Update
            </button>
            <button
              class="btn btn-sm btn-danger"
              @click="handleDelete(product)"
            >
              Delete
            </button>
          </td>

          <td v-else>
            <button class="btn btn-sm btn-primary" @click="handleSave(product)">
              Save
            </button>
            <button class="btn btn-sm btn-danger" @click="updateItemId = null">
              Cancel
            </button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  name: "product-list",
  data() {
    return { updateItemId: null };
  },
  props: {
    products: Array,
  },
  methods: {
    handleDelete(product) {
      this.$emit("delete:product", product);
    },
    handleUpdate(product) {
      this.updateItemId = product.id;
    },
    handleSave(product) {
      this.$emit("update:product", product);
      this.updateItemId = null;
    },
  },
});
</script>

<style scoped>
.product-list {
  margin:10px 200px
}
</style>
