<template>
  <div class="container">
   <h1 class="title">Home Page</h1>
   <p class="subtitle">
     Lorem ipsum dolor, sit amet consectetur adipisicing elit. Repudiandae molestias dolorem id iure eius! Explicabo error fugit dignissimos repellat quod, quo corrupti placeat sed, illum provident recusandae ut voluptates quaerat! Lorem ipsum dolor sit, amet consectetur adipisicing elit. Ipsa autem repellendus sunt cum mollitia expedita sapiente? Accusamus, incidunt velit laboriosam atque ut mollitia quos obcaecati corporis ex ab deleniti fuga.
   </p>
 
   <div class="button-container">
     <nuxt-link to="/products" tag="a" class="button--green">Products</nuxt-link>
     <a href="#" class="button--green">Product</a>
   </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.container {
  margin: 0 auto;
  min-height: 100vh;
  justify-content: center;
  text-align: center;
  margin-top: 50px;
}
.button-container{
  border: 1px solid #392;
  background-color: #dedede;
  padding: 10px;
  margin-top: 50px;
  box-shadow: 2px 3px 8px rgba(0,0,0,.1);
  display: flex;
  justify-content: center;
}
.button--green{
  margin-left: 5px;
}
.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 30px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

</style>
