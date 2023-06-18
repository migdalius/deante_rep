<template>
  <section id="description" class="page-description">
    <h2 class="page-title">Opis produktu</h2>
    <p class="page-desc">
      {{ product.description }}
    </p>

    <div v-for="(feature, index) in product.features" :key="feature.name">
      <div
        class="description-with-img"
        v-if="feature.image !== '' && feature.description !== ''"
      >
        <div class="description-img" v-if="index % 2 === 0">
          <img :src="feature.image" alt="" />
        </div>
        <div class="main-description">
          <h4>{{ feature.name }}</h4>
          <p>{{ feature.description }}</p>
        </div>
        <div class="description-img second" v-if="index % 2 === 1">
          <img :src="feature.image" alt="" />
        </div>
      </div>
      <div
        class="description-mobile"
        v-if="feature.image !== '' && feature.description !== ''"
      >
        <div class="description-img">
          <img :src="feature.image" alt="" />
        </div>
        <div class="main-description">
          <h4>{{ feature.name }}</h4>
          <p>{{ feature.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
  export default {
    name: "MainDescription",
    props: ["product"],
  };
</script>
