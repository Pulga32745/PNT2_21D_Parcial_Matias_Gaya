<template>
  <div class="container mt-5">
    <h2 class="mb-4">Conversor de Temperatura</h2>

    <div class="form-group">
      <label for="tempC">Ingrese Temperatura °C:</label>
      <input
        id="tempC"
        type="number"
        class="form-control w-25"
        v-model.number="celsius"
      />
    </div>

    <p :style="{ color: colorTexto }">
      Conv. Temperatura °F: {{ fahrenheit }}
    </p>

    <p :style="{ color: colorTexto }">
      Conv. Temperatura °K: {{ kelvin }}
    </p>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      celsius: 0
    };
  },
  computed: {
    fahrenheit() {
      return ((this.celsius * 9) / 5 + 32).toFixed(2);
    },
    kelvin() {
      return (this.celsius + 273.15).toFixed(2);
    },
    colorTexto() {
      if (this.celsius <= 0) return "blue";
      else if (this.celsius < 15) return "magenta";
      else return "red";
    }
  }
};
</script>

<style>
body {
  background-color: #f8f9fa;
}
h2 {
  font-weight: bold;
}
</style>


