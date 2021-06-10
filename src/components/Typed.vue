<template>
    <vue-typed-js :strings="['\'I\'m available\'', '\'Ready to work\'']" :loop="true" :typeSpeed="100" :backSpeed="50">
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;status:&nbsp;&nbsp;<p class='typing'></p>
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

