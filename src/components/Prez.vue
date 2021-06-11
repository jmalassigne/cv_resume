<template>
  <div class="componentPrez">
    <div class="componentPrez__container">
      <h1>Prssentation</h1>
    </div>
  </div>
</template>

<script>
export default {
  name: "Prez",
};
</script>

<style lang="scss" scoped>
@import "../styles/_variables.scss";

.componentPrez {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;

  &__container {
    width: 80%;
    background: $background_1;
    height: 80%;
    border-radius: 10px;
  }
}


</style>
