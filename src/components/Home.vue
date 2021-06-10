<template>
  <div class="component-container">
    <header class="component-header">
      <h2 class="component-header__h2">
        <span class="component-header__h2-item">Julien</span><br /><span
          class="component-header__h2-item"
          >Malassigne</span
        >
      </h2>
      <h3 class="component-header__h3">Developpeur web</h3>
      <h3 class="component-header__h3">Full Stack</h3>
    </header>
    <div class="lorem-container">
       <p>&lt;<span style="color: #FFC108">script</span>&gt;</p><br>
        <p>&nbsp;&nbsp;&nbsp;const myFunction = () => {</p><br>
        <p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return {</p><br>
        <p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;job: 'Web development',</p><br>
        <p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;languages: ['php', 'javascript'],</p><br>
        <Typed /><br>
        <p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}</p>
        <p>&nbsp;&nbsp;&nbsp;}</p>
      <p>&lt;<span style="color: #FFC108">script</span>&gt;</p>
    </div>
    <button class="starting__button" @click.prevent="$emit('openNav')">
      <i class="fas fa-sign-in-alt"></i>
      <p>Commencer la visite</p>
    </button>
  </div>
</template>

<script>
import Typed from "./Typed.vue";

export default {
  name: "Home",
  components: {
    Typed,
  },
};
</script>

<style lang="scss" scoped>
@import "../styles/_variables.scss";

.component-container {
  position: relative;
  padding: 30px;
  height: 100%;
  width: 100%;

  .starting__button {
    cursor: pointer;
    position: absolute;
    display: flex;
    align-items: center;
    justify-content: center;
    bottom: 100px;
    left: 50%;
    transform: translateX(-50%);
    height: 50px;
    width: 250px;
    border-radius: 2px;
    border: none;
    background: $yellow;
    font-size: 1rem;

    i {
      opacity: 0;
      margin: 10px;
      transform: translateY(20px) translateX(-20px);
      transition: all 0.3s;
    }

    p {
      transform: translateX(-18px);
      transition: all 0.3s;
    }

    &:hover {
      i {
        opacity: 1;
        transform: translateY(0);
      }

      p {
        transform: translateY(0);
      }
    }
  }
}

.component-header {
  position: absolute;
  right: 50px;
  top: 100px;

  &__h2 {
    color: $yellow;
    font-size: 4rem;
    font-weight: 700;
    line-height: 5rem;
    text-shadow: 6px 3px 0px #000000;
  }

  &__h3 {
    font-size: 2rem;
    line-height: 3rem;
    letter-spacing: 3px;
  }
}
</style>
