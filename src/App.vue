<script>
var jsonURL = "https://raw.githubusercontent.com/ridwanazeez/colourpalettes-JSONs/master/all-palettes.json";

export default {
  data() {
    return {
      colours: [],
    };
  },
  mounted() {
    fetch(jsonURL)
      .then((response) => response.json())
      .then((data) => (this.colours = data));
  },
};
</script>

<template>
  <div v-for="item in colours">
    <div v-for="colour in item.colours">
      <p v-bind:style="{ color: colour.hex }">{{ colour.hex }}</p>
    </div>
  </div>
</template>

<style></style>
