<template>
  <div>
    <button @click="Api1">Mostrar api1</button>
    <pre v-if="rawData">{{ rawData }}</pre>

    <button @click="Api2">Mostrar api2</button>
    <pre v-if="rawData">{{ rawData }}</pre>
    <button @click="Api3">Mostrar api3</button>
    <pre v-if="rawData">{{ rawData }}</pre>

    <button @click="Api4">Mostrar api4</button>
    <pre v-if="rawData">{{ rawData }}</pre>

  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      rawData: null
    };
  },
  methods: {
    Api1() {
      axios.get('https://countriesnow.space/api/v0.1/countries/population')
        .then(response => {
          this.rawData = JSON.stringify(response.data, null, 2); 
        })
        .catch(() => {
          this.error = 'Error al obtener los datos'; 
        });
    },
    Api2() {
      axios.get('https://api.jikan.moe/v4/random/anime')
        .then(response => {
          this.rawData = JSON.stringify(response.data, null, 2); 
        })
        .catch(() => {
          this.error = 'Error al obtener los datos'; 
        });
    },
    Api3() {
      axios.get('https://api.jikan.moe/v4/recommendations/anime')
        .then(response => {
          this.rawData = JSON.stringify(response.data, null, 2); 
        })
        .catch(() => {
          this.error = 'Error al obtener los datos'; 
        });
    },
    Api4() {
      axios.get('https://api.jikan.moe/v4/random/manga')
        .then(response => {
          this.rawData = JSON.stringify(response.data, null, 2); 
        })
        .catch(() => {
          this.error = 'Error al obtener los datos'; 
        });
    }
  }
};
</script>

<style scoped>
pre {
  background-color: #f4f4f4;
  padding: 10px;
  border: 1px solid #ddd;
  overflow-x: auto;
}
</style>
