<template>
    <div>
        <template v-if='notes.length'>
            <Notas v-for='(note, i) in notes' :key='note.text'
                :note='note'
                @noteDeleted="$emit('noteDeleted', i)"
            ></Notas>
        </template>
        <p v-else>Nenhuma nota adicionada</p>
    </div>
</template>

<script>
import Notas from './Notas.vue'

export default {
    name: 'NoteGrid',
    components: { Notas },
    props: {
        notes: { type: Array, require: true }
    }
}
</script>

<style scoped lang="scss">
p {
    font: 300 28px 'Roboto', sans-serif;
}
</style>