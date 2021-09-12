<template>
  <div class="form-element">
    <input type="text" v-model="text" placeholder="Nova nota" />
    <button @click="add" class="btnAdc">Adicionar nova nota</button>
  </div>
</template>

<script>
export default {
  name: "NewNote",
  data() {
    return {
      text: "",
    };
  },
  methods: {
    add() {
      this.text == ""
        ? this.Mensagem("Por favor, preencha o campo")
        : this.$emit("noteAdded", { text: this.text });
      this.text = "";
    },
    Mensagem(texto) {
      this.$toasted.show(texto, {
        theme: "bubble",
        position: "bottom-center",
        duration: 2000,
      });
    },
  },
};
</script>

<style lang="scss">
.btnAdc {
  background: #fe7144;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  border-radius: 4px;
  border: none;
  color: #fff;
  width: 450px;
  height: 50px;
  font: 100 22px "Roboto", sans-serif;
  cursor: pointer;
  transition: filter 0.2s;
  margin-top: 10px;

  &:hover {
    filter: brightness(0.9);
  }
}

.form-element {
  outline: none;
  font-size: 2rem;
  padding: 5px 10px 8px;
  color: #fff;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;

  input {
    width: 500px;
    height: 30px;
    border-radius: 2px;
    border: none;
    outline: none;
    font-size: 1.4rem;
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.15);
    padding: 5px 12px;
  }
}
</style>