<template>
  <div id="App">
    <ProductPage />
  </div>
</template>

<script>
  import ProductPage from "./ProductPage.vue";
  import "./main.css";

  export default {
    name: "App",
    components: {
      ProductPage,
    },
  };
</script>
