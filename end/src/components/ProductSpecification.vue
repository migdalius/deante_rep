<template>
  <section id="specification" class="page-specification">
    <h2 class="page-title">Specyfikacja Produktu</h2>

    <table
      v-for="(values, key) in parametersGroup"
      :key="key"
      class="styled-table"
    >
      <thead>
        <tr>
          <th colspan="2">{{ key }}</th>
        </tr>
      </thead>

      <tbody>
        <tr v-for="(value, name) in values" :key="name">
          <td>{{ name }}</td>
          <td>{{ value }}</td>
        </tr>
      </tbody>
    </table>
  </section>
</template>

<script>
  export default {
    name: "ProductSpecification",
    props: ["product"],
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
