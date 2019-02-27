<template>
  <div>
    <p>Total Vagas: {{ totalVagas }}</p>
    <p>Vagas Ocupadas: {{ ocupadaVagas }}</p>
    <p>Vagas Disponíveis: {{ disponivelVagas }}</p>
    <div class="">
      <button type="button" name="button" @click="ocuparVaga()">Entrar</button>
      <button type="button" name="button" @click="desocuparVaga()">Sair</button>
    </div>
    <p>{{ alert }}</p>
  </div>
</template>

<script>
export default {
  name: 'Parking',
  data () {
    return {
      totalVagas: 10,
      ocupadaVagas: 0,
      disponivelVagas: 0,
      alert: '',
    }
  },
  mounted: function () {
    this.disponivelVagas = this.totalVagas
  },
  methods: {
    ocuparVaga: function () {
      if (this.ocupadaVagas < this.totalVagas) {
        this.ocupadaVagas = this.ocupadaVagas + 1;
        this.disponivelVagas = this.disponivelVagas - 1;
      }
    },
    desocuparVaga: function () {
      if (this.ocupadaVagas > 0) {
        this.ocupadaVagas = this.ocupadaVagas - 1;
        this.disponivelVagas = this.disponivelVagas + 1;
      }
    },
  },
  watch: {
    disponivelVagas: function () {
      if (this.disponivelVagas <= 0) {
        this.alert = 'Estacionamento cheio!';
      }
      else {
        this.alert = '';
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
button {
  margin: 10px;
}
</style>
