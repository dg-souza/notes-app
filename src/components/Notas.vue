<template>
  <div class="content">
    <div class="note">
        asdaasdasd
    </div>
  </div>
</template>

<script>
export default {
  name: "Notas",
};
</script>

<style lang="scss">
.content {
    max-width: 1120px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.note {
  background: #cac8c8;
  border-radius: 8px;
  box-shadow: 0 2px 12px rgba(0, 0, 0, 0.04);
  padding: 24px;

  margin-top: 32px;
}
</style>