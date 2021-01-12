<template>
 <div class="container">
    <SearchProduct/>
    <nuxt-child/>
 </div>
</template>

<script>
import SearchProduct from "@/components/SearchProduct"
  export default {
      layout:"product",
    components:{
        SearchProduct,
    }
    }
</script>

<style scoped>

</style>