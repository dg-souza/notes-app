<template>
    <div class="note">
        <span @click="$emit('noteDeleted', note)">🗑️</span>
        <p>{{ note.text }}</p>
    </div>
</template>

<script>
export default {
    props: {
        note: { type: Object, require: true }
    },
    name: "Notas",
};
</script>

<style lang="scss">
.note {
  background: #fff;
  border-radius: 8px;
  box-shadow: 0 2px 12px rgba(0, 0, 0, 0.04);
  padding: 24px;
  width: 500px;
  position: relative;
  justify-content: center;
  align-items: center;

  margin-top: 32px;

p {
    font: 300 24px 'Roboto', sans-serif;
}

  span {
      position: absolute;
      display: flex;
      justify-content: flex-end;
      right: 10px;
      top: 10px;
      cursor: pointer;
  }
}
</style>