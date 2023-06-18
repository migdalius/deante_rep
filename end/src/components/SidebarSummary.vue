<template>
  <div class="product-price">
    <div class="sidebar-container">
      <h1>{{ product.name }}</h1>
      <p>Kod Produktu: {{ product.id }}</p>
      <p>
        Marka: <strong>{{ product.brand }}</strong>
      </p>
      <hr />
      <div v-if="product.prices.hasPromotion" class="discount">
        <span class="promotion">Promocja</span>
        <div class="old-price">
          <del>{{ product.prices.grossPrice.toFixed(2) }} zł</del>
          <span>Najniższa cena z 30 dni przed obniżką</span>
        </div>
        <p class="discount-price">
          {{ product.prices.promotion.grossPrice.toFixed(2) }} zł
        </p>
      </div>
      <div v-else class="discount">
        <span class="regular-price"
          >{{ product.prices.promotion.grossPrice.toFixed(2) }} zł</span
        >
      </div>
      <hr />
      <p>Liczba sztuk</p>
      <div class="product-counter">
        <div class="counter">
          <button @click="decrementCounter">-</button>
          <input v-model="quantity" />
          <button @click="incrementCounter">+</button>
        </div>
        <p>Dostępny od zaraz!</p>
      </div>
      <div class="buy-container">
        <ProductButton :text="'Dodaj do koszyka'" />
        <div class="line-with-text">
          <div></div>
          <p>Lub</p>
          <div></div>
        </div>
        <ProductButton :text="'Kup u partnera'" />
      </div>
    </div>
  </div>
</template>

<script>
  import ProductButton from "./ProductButton.vue";
  export default {
    name: "SidebarSummary",
    props: ["product"],
    components: {
      ProductButton,
    },
    data() {
      return {
        quantity: 1,
      };
    },
    methods: {
      decrementCounter() {
        if (this.quantity > 1) {
          this.quantity--;
        }
      },
      incrementCounter() {
        this.quantity++;
      },
    },
  };
</script>
