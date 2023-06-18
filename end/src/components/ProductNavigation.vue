<template>
  <nav class="page-navigation">
    <div
      :class="['navigation', activeSection === 'description' ? 'active' : '']"
      @click="scrollToSection('description')"
    >
      Opis
    </div>
    <div
      :class="['navigation', activeSection === 'specification' ? 'active' : '']"
      @click="scrollToSection('specification')"
    >
      Specfikacja
    </div>
    <div
      :class="['navigation', activeSection === 'downloads' ? 'active' : '']"
      @click="scrollToSection('downloads')"
    >
      Pliki do pobrania
    </div>
  </nav>
</template>

<script>
  export default {
    name: "ProductNavigation",
    data() {
      return {
        activeSection: "description",
      };
    },
    methods: {
      scrollToSection(sectionId) {
        const section = document.getElementById(sectionId);
        if (section) {
          section.scrollIntoView({ behavior: "smooth" });
          this.activeSection = sectionId;
        }
      },
    },
  };
</script>
