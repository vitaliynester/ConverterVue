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
    // Метод для перевода Футов в Метры
    convertFtToM: (value) => {
      if (isNaN(value)) {
        return 0;
      }
      return value / 3.281;
    },
    // Метод для перевода морских миль в километры
    convertNmToKm: (value) => {
      if (isNaN(value)) {
        return 0;
      }
      return value / 1.852;
    },
    // Метод для перевода градусов в радианы
    convertDegreeToRadians: (value) => {
      if (isNaN(value)) {
        return 0;
      }
      return value * (Math.PI / 180);
    },
    // Метод для перевода температура по Цельсию в температуру по Фаренгейту
    convertCelsiusToFahrenheit: (value) => {
      if (isNaN(value)) {
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