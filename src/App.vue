<template>
  <div id="app">
    <h1>Bem vindo ao aplicativo de notas</h1>
    <button @click="Adc" class='btnAdc'>Adicionar nova nota</button>

    <div class='list-notes'>
      <Notas />
    </div>
  </div>
</template>

<script>
import Notas from './components/Notas.vue'

export default {
  name: 'App',
  components: {
    Notas
  },
  data() {
    return {

    }
  },
  methods: {
    Adc() {
      alert('teste')
    }
  }
}
</script>

<style lang="scss">
#app {
  h1 {
    font: 300 28px 'Roboto', sans-serif;
    text-align: start;
  }
}

.btnAdc {
  background: #AD7AC6;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  border-radius: 4px;
  border: none;
  color: #fff;
  width: 200px;
  height: 50px;
  font: 100 18px 'Roboto', sans-serif;
  cursor: pointer;
  transition: filter 0.2s;

  &:hover {
    filter: brightness(0.9);
  }
}

.list-notes {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
</style>
