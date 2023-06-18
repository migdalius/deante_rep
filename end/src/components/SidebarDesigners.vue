<template>
  <div v-if="product.isDesigned" class="designer-container">
    <div class="designer">
      <h2>Projektanci</h2>
      <hr />

      <div
        v-for="designer in product.designers"
        :key="designer.name"
        class="designer-content"
      >
        <div>
          <img
            src="https://deante.b-cdn.net/_MARKETING/PROJEKTANCI/Maria-Warenik_b-w_small_43063_hd.jpg?width=300&height=200"
            alt=""
          />
          <h3>{{ designer.name }}</h3>
        </div>
        <p>
          {{ designer.description }}
        </p>
      </div>
    </div>
  </div>
</template>

<script>
  import { product } from "../data.js";
  export default {
    name: "SidebarDesigners",

    data() {
      return {
        product: product,
        selectedImage: product.images[0].src,
        thumbnail: "",
        isContainerHidden: false,
        messages: {
          pl: {
            instruction: "Instrukcja",
            technicalDrawing: "Rysunek techniczny",
            model3d: "Model 3D",
            warrantyCard: "Karta gwarancyjna",
            hygienicCertificate: "Atest higieniczny",
            declaration: "Deklaracja właściwości użytkowych",
          },
        },
      };
    },
    methods: {
      showImage(src) {
        this.selectedImage = src;
      },
    },
    computed: {
      parametersGroup() {
        let categories = this.product.properties;
        const groups = categories.reduce((acc, obj) => {
          const key = obj.scope;
          const name = obj.name;
          const value = obj.value;
          const curGroup = acc[key] ?? {};
          return { ...acc, [key]: { ...curGroup, [name]: value } };
        }, {});

        return groups;
      },
    },
  };
</script>
