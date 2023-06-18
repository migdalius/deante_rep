<template>
  <div class="sidebar">
    <SidebarSummary :product="product" />
    <SidebarDesigners :product="product" />
  </div>
</template>

<script>
  import SidebarSummary from "./SidebarSummary.vue";
  import SidebarDesigners from "./SidebarDesigners.vue";

  export default {
    name: "SidebarContainer",
    props: ["product"],
    components: {
      SidebarSummary,
      SidebarDesigners,
    },
  };
</script>
