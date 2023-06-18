<template>
  <div class="img-container">
    <div class="trumbnail-wrapper">
      <div
        v-for="thumbnail in product.images"
        :key="thumbnail.src"
        class="trumbnail"
        @click="showImage(thumbnail.src)"
      >
        <img :src="thumbnail.src" alt="" />
      </div>
    </div>
    <div class="image-wrapper">
      <img :src="selectedImage" alt="" />
    </div>
  </div>
</template>

<script>
  export default {
    name: "ProductGallery",
    props: ["product"],
    data() {
      return {
        selectedImage: this.product.images[0].src,
      };
    },
    methods: {
      showImage(src) {
        this.selectedImage = src;
      },
    },
  };
</script>
