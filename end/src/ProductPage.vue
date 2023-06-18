<template>
  <main class="product">
    <div class="container">
      <MainContainer :product="product" />
      <SidebarContainer :product="product" />
    </div>
  </main>
</template>

<script>
  import { product } from "./data.js";
  import MainContainer from "./components/MainContainer.vue";
  import SidebarContainer from "./components/SidebarContainer.vue";

  export default {
    name: "ProductPage",
    components: {
      MainContainer,
      SidebarContainer,
    },
    data() {
      return {
        product: product,
      };
    },
  };
</script>
