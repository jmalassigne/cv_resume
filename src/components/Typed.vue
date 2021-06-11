<template>
    <vue-typed-js class="typed-container" :strings="['\'I \'m available\'', '\'Ready to work\'']" :loop="true" :typeSpeed="100" :backSpeed="50">
      <p class='typing'></p>
    </vue-typed-js>
</template>

<script>
import Vue from "vue";
import VueTypedJs from "vue-typed-js";

Vue.use(VueTypedJs);

export default {
    name: 'Typed'
};
</script>

<style  scoped>
.typed-container {
  position: relative;
  left: 100px;
  top: -18px;
}
</style>>


