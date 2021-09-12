<template>
  <div id="app">
    <h1>Bem vindo ao aplicativo de notas</h1>
    <NewNote @noteAdded='addNote' />
    <NoteGrid :notes='notes' @noteDeleted='deleteNote' />
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
      notes: []
    };
  },
  methods: {
    Adc() {
      alert("teste");
    },
    addNote(note) {
      const sametext = t => t.text === note.text
      const reallyNew = this.notes.filter(sametext).length == 0

      if(reallyNew) {
        this.notes.push({
          text: note.text
        })
      }
    },
    deleteNote(i) {
      this.notes.splice(i, 1)
    }
  },
  created() {
    this.notes = []
  }
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
