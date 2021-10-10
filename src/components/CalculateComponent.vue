<template>
<div class="mt-5">
  <h3 class="text-center">{{name}}</h3>

  <div class="input-group mb-3 text-center">
    <input type="text" class="form-control" :placeholder="inputPlaceholder" v-model="sourceValue">
    <span class="input-group-text">⇋</span>
    <input type="text" class="form-control" :placeholder="outputPlaceholder" :value="convert">
  </div>

</div>
</template>

<script>
export default {
  name: "CalculateComponent",
  data: () => {
    return {
      sourceValue: 0.0,
      convertedValue: 0.0,
    }
  },
  props: {
    name: String,
    inputPlaceholder: String,
    outputPlaceholder: String,
    convertFunction: Function,
  },
  computed: {
    convert () {
      return this.convertFunction(this.sourceValue);
    }
  },
}
</script>

<style scoped>
h3 {
  font-weight: bold;
}
</style>