<template>
  <div>
    <input type="number" name="" value="" v-model="number">
    <button type="button" name="button" @click="cousinNumber()">Listar Números Primos</button>
    <p v-for="result in results" :key="result">{{ result }}</p>
  </div>
</template>

<script>
export default {
  name: 'CousinNumber',
  data () {
    return {
      number: null,
      results: [],
    }
  },
  //
  methods: {
    cousinNumber: function () {
      this.results = [];
      for (var i = 1; i <= this.number; i++) {
        var count = 0;
        for (var y = 1; y <= i; y++) {
          if ((i % y) == 0) {
            count = count + 1
          }
        }
        if (count == 2) {
          this.results.push(i);
        }
      }
    }
  }
}
</script>

<style scoped>

</style>
