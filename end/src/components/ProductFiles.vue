<template>
  <section id="downloads" class="page-download">
    <h2 class="page-title">Pliki do Pobrania</h2>
    <div class="table-container">
      <table class="styled-table">
        <thead>
          <tr>
            <th>Rodzaj Pliku</th>
            <th>Nazwa Pliku</th>
            <th>Rozszerzenie</th>
            <th></th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="file in product.files" :key="file.src">
            <td>{{ messages.pl[file.type] }}</td>
            <td>{{ decodeURIComponent(file.src.split("/").pop()) }}</td>
            <td>{{ file.src.slice(-3).toUpperCase() }}</td>
            <td>
              <a :href="file.src" target="_blank">
                <button class="download-button">Pobierz</button>
              </a>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </section>
</template>

<script>
  export default {
    name: "ProductFiles",
    props: ["product"],
    data() {
      return {
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
  };
</script>
