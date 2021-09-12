<template>
  <div id="app">
    <h1>Bem vindo ao aplicativo de notas</h1>
    <NewNote @noteAdded="addNote" />
    <NoteGrid :notes="notes" @noteDeleted="deleteNote" />
  </div>
</template>

<script>
import NoteGrid from "./components/NoteGrid.vue";
import NewNote from "./components/NewNote.vue";

export default {
  name: "App",
  components: {
    NoteGrid,
    NewNote,
  },
  data() {
    return {
      notes: [],
    };
  },
  watch: {
    notes: {
      deep: true,
      handler() {
        localStorage.setItem("notes", JSON.stringify(this.notes));
      },
    },
  },
  methods: {
    addNote(note) {
      const sametext = (t) => t.text === note.text;
      const reallyNew = this.notes.filter(sametext).length == 0;

      if (reallyNew) {
        this.notes.push({
          text: note.text,
        });
        this.Mensagem("Nova nota adicionada :)");
      } else this.Mensagem("Que tal digitar algo diferente para a nova nota?");
    },
    deleteNote(i) {
      this.notes.splice(i, 1);
      this.Mensagem("Nota deletada com sucesso.");
    },
    Mensagem(texto) {
      this.$toasted.show(texto, {
        theme: "bubble",
        position: "bottom-center",
        duration: 2000,
      });
    },
  },
  created() {
    const json = localStorage.getItem("notes");
    const array = JSON.parse(json);
    this.notes = Array.isArray(array) ? array : [];
  },
};
</script>

<style lang="scss">
body {
  background: rgb(245, 237, 237);
}

#app {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;

  h1 {
    font: 300 28px "Roboto", sans-serif;
  }
}
</style>
