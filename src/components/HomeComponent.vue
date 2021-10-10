<template>
  <div class="container">
    <h1 class="title">
      {{ name }}
    </h1>
    <CalculateComponent name="Футы в метры"
                        :convert-function="convertFtToM"
                        input-placeholder="Футы"
                        output-placeholder="Метры"/>

    <CalculateComponent name="Морские мили в километры"
                        :convert-function="convertNmToKm"
                        input-placeholder="Морские мили"
                        output-placeholder="Километры"/>

    <CalculateComponent name="Градусы в радианы"
                        :convert-function="convertDegreeToRadians"
                        input-placeholder="Градусы"
                        output-placeholder="Радианы"/>

    <CalculateComponent name="Температура по Цельсию в температуру по Фаренгейту"
                        :convert-function="convertCelsiusToFahrenheit"
                        input-placeholder="Температура по Цельсию"
                        output-placeholder="Температура по Фаренгейту"/>
  </div>
</template>

<script>
import CalculateComponent from "@/components/CalculateComponent";

export default {
  name: "HomeComponent",
  components: {CalculateComponent},
  props: {
    name: String
  },
  methods: {
    convertFtToM: (value) => {
      if (typeof(value) == 'number') {
        return 0;
      }
      return value / 3.281;
    },
    convertNmToKm: (value) => {
      if (typeof(value) == 'number') {
        return 0;
      }
      return value / 1.852;
    },
    convertDegreeToRadians: (value) => {
      if (typeof(value) == 'number') {
        return 0;
      }
      return value * (Math.PI / 180);
    },
    convertCelsiusToFahrenheit: (value) => {
      if (typeof(value) == 'number') {
        return 0;
      }
      return (value * 9/5) + 32;
    },
  }
}
</script>

<style scoped>
.title {
  font-style: italic;
}
</style>