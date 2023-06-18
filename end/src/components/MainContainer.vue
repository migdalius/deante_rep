<template>
  <div class="main-content">
    <ProductGallery :product="product" />
    <ProductNavigation />
    <hr />
    <MainDescription :product="product" />
    <hr />
    <ProductSpecification :product="product" />
    <hr />
    <ProductFiles :product="product" />
  </div>
</template>

<script>
  import ProductGallery from "../components/ProductGallery.vue";
  import ProductNavigation from "../components/ProductNavigation.vue";
  import MainDescription from "../components/MainDescription.vue";
  import ProductSpecification from "../components/ProductSpecification.vue";
  import ProductFiles from "../components/ProductFiles.vue";
  export default {
    name: "MainContainer",
    props: ["product"],
    components: {
      ProductGallery,
      ProductNavigation,
      MainDescription,
      ProductSpecification,
      ProductFiles,
    },
  };
</script>
