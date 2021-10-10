<template>
  <div id="app">
    <HomeComponent name="Форма быстрого перевода из одной единицы измерения в другую" />
  </div>
</template>

<script>
import HomeComponent from "@/components/HomeComponent";

export default {
  name: 'App',
  components: {
    HomeComponent,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
