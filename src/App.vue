<template>
  <div id="app">
    <div v-if="isLoading">
      <div class="loading">
        <h1 class="loading__heading">julien malassigne</h1>
        <div class="loading__bar">
          <div
            class="loading__bar-item"
            :class="{ start: startProgress }"
          ></div>
        </div>
        <p>{{ progress }} %</p>
      </div>
    </div>
    <div v-else class="main-page" ref="mainPage">
      <aside class="left-aside">
        <header class="header">
          <div class="header__img">
            <img src="./assets/pp.jpg" alt="" />
          </div>
          <h1 class="header__name">julien malassigne</h1>
          <h2>développeur web</h2>
          <h3>full stack</h3>
          <p></p>
        </header>
        <div class="main">
          <div class="main__location">
            <h3>Pays: <span>France</span></h3>
            <h2>Ville: <span>Saint-Brieuc</span></h2>
            <p>Age: <span>29</span></p>
          </div>
          <hr />
          <div class="main__languages">
            <div class="main__languages-item">
              <div class="round">100%</div>
              <p>Francais</p>
            </div>
            <div class="main__languages-item">
              <div class="round second">75%</div>
              <p>Anglais</p>
            </div>
            <div class="main__languages-item">
              <div class="round third">50%</div>
              <p>Italien</p>
            </div>
          </div>
          <hr />
          <div class="main__code">
            <div class="main__code-item">
              <h4>HTML <span>80%</span></h4>
              <div class="bar">
                <div class="bar-item first"></div>
              </div>
            </div>
            <div class="main__code-item">
              <h4>CSS <span>70%</span></h4>
              <div class="bar">
                <div class="bar-item second"></div>
              </div>
            </div>
            <div class="main__code-item">
              <h4>JavaScript <span>70%</span></h4>
              <div class="bar">
                <div class="bar-item third"></div>
              </div>
            </div>
            <div class="main__code-item">
              <h4>PHP <span>50%</span></h4>
              <div class="bar">
                <div class="bar-item fourth"></div>
              </div>
            </div>
            <div class="main__code-item">
              <h4>Wordpress <span>40%</span></h4>
              <div class="bar">
                <div class="bar-item fifth"></div>
              </div>
            </div>
          </div>
          <hr />
          <div class="main__knowledge">
            <h5><i class="fas fa-check"></i>Bootstrap</h5>
            <h5><i class="fas fa-check"></i>SASS</h5>
            <h5><i class="fas fa-check"></i>Git et Github</h5>
            <h5><i class="fas fa-check"></i>VueJS</h5>
            <h5><i class="fas fa-check"></i>NodeJS</h5>
          </div>
          <hr />
          <div class="main__cv">
            <a>Télécharger mon CV<i class="fas fa-download"></i></a>
          </div>
        </div>
        <footer class="footer">
          <a href="#"><i class="fab fa-linkedin"></i></a>
          <a href="#"><i class="fab fa-github-square"></i></a>
        </footer>
      </aside>
      <main class="container" :class="{ open: openedNav }">
        <Prez v-if="activeComponent === 'prez'" />
        <Skills v-if="activeComponent === 'skills'" />
        <Templates v-if="activeComponent === 'templates'" />
        <Contact v-if="activeComponent === 'contact'" />
      </main>
      <aside class="right-aside" :class="{ open: openedNav }">
        <div class="top">
          <div class="top__container" @click.prevent="openedNav = !openedNav">
            <div class="top__container-item"></div>
            <div class="top__container-item"></div>
            <div class="top__container-item"></div>
          </div>
        </div>
        <nav class="nav">
          <ul>
            <li class="nav__item" @click.prevent="nav('prez')">Présentation</li>
            <li class="nav__item" @click.prevent="nav('skills')">Compétences</li>
            <li class="nav__item" @click.prevent="nav('templates')">Templates</li>
            <li class="nav__item" @click.prevent="nav('contact')">Contact</li>
          </ul>
        </nav>
      </aside>
    </div>
  </div>
</template>

<script>
import Prez from "./components/Prez.vue";
import Skills from "./components/Skills.vue";
import Templates from "./components/Templates.vue";
import Contact from "./components/Contact.vue";

export default {
  name: "App",
  components: {
    Prez,
    Skills,
    Templates,
    Contact
  },
  data() {
    return {
      isLoading: true,
      startProgress: false,
      progress: 0,
      openedNav: false,
      activeComponent: 'prez'
    };
  },
  mounted() {
    setTimeout(() => {
      this.startProgress = true;
    }, 500);

    setInterval(() => {
      if (this.progress < 100) {
        this.progress++;
      }
    }, 20);

    setTimeout(() => {
      this.isLoading = !this.isLoading;
    }, 3000);
  },
  methods: {
    nav(target) {
      this.activeComponent = target;
      this.openedNav = false;
    }
  }
};
</script>

<style lang='scss'>
@import "./styles/_variables.scss";
@import "./styles/_keyframes.scss";

/********** Reset **********/

html,
body,
p,
ol,
ul,
li,
dl,
dt,
dd,
blockquote,
figure,
fieldset,
legend,
textarea,
pre,
iframe,
hr,
h1,
h2,
h3,
h4,
h5,
h6 {
  margin: 0;
  padding: 0;
}
h1,
h2,
h3,
h4,
h5,
h6 {
  font-size: 100%;
  font-weight: normal;
}
ul {
  list-style: none;
}
button,
input,
select {
  margin: 0;
}
html {
  box-sizing: border-box;
}
*,
*::before,
*::after {
  box-sizing: inherit;
}
img,
video {
  height: auto;
  max-width: 100%;
}
iframe {
  border: 0;
}
table {
  border-collapse: collapse;
  border-spacing: 0;
}
td,
th {
  padding: 0;
}

/********** Global styles **********/

html {
  background-color: $background_1;
}

body {
  color: $white_para;
  font-size: 13px;
  font-weight: 400;
  line-height: 25px;
  padding: 20px;
  font-family: "poppins", sans-serif;
}

h1,
h2,
h3,
h4,
h5,
h6 {
  color: $white_heading;
}

a {
  text-decoration: none;
  color: inherit;
}

/********** Loading **********/

.loading {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  width: 200px;
  height: 100px;
  margin: 50vh auto;

  &__heading {
    font-size: 1.3rem;
    text-transform: capitalize;
    font-weight: 600;
  }

  &__bar {
    width: 100%;
    height: 5px;
    border-radius: 3px;
    background-color: $background_2;

    &-item {
      width: 0;
      height: 100%;
      background-color: $yellow;
      transition: width 2s;

      &.start {
        width: 100%;
      }
    }
  }
}

/********** Main Page **********/
.main-page {
  display: flex;
  max-width: 1500px;
  height: calc(100vh - 60px);
  margin-left: auto;
  margin-right: auto;
  overflow: hidden;
}

/********** Asides **********/

aside {
  width: 280px;
  background-color: $background_3;
  flex: none;
}

/********** Left Aside **********/

.left-aside {
  height: 100%;
  overflow-y: scroll;
}

.header {
  position: fixed;
  z-index: 3;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  width: 280px;
  height: 230px;
  padding: 25px 0;
  background-color: rgba($color: $background_2, $alpha: 0.9);
  text-transform: capitalize;

  &__img {
    position: relative;
    height: 90px;
    width: 90px;
    border-radius: 50%;

    &:after {
      position: absolute;
      bottom: 2px;
      right: 2px;
      content: "";
      width: 20px;
      height: 20px;
      background-color: $yellow;
      border-radius: 50%;
      animation: pulse 1.5s infinite;
    }

    img {
      width: inherit;
      height: inherit;
      border-radius: inherit;
    }
  }

  &__name {
    font-size: 14px;
    font-weight: 600;
    margin: 5px;
  }
  h2,
  h3 {
    color: $white_para;
  }
}

.main {
  margin-top: 230px;
  margin-bottom: 50px;
  padding: 20px 30px;
  width: 100%;

  hr {
    margin: 20px 0;
    border-top: none;
    border-color: rgba($color: #fff, $alpha: 0.2);
  }

  &__location {
    color: $white_heading;

    span {
      float: right;
      color: $white_para;
    }
  }

  &__languages {
    display: flex;
    justify-content: space-between;

    &-item {
      text-align: center;

      p {
        color: $white_heading;
      }

      .round {
        position: relative;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 50px;
        width: 50px;
        border-radius: 50%;
        border: 4px solid $yellow;
        margin: 20px 0;

        &.second:after {
          content: "";
          position: absolute;
          background-color: $background_3;
          clip-path: polygon(
            22% 69%,
            37% 43%,
            62% 23%,
            100% 12%,
            100% 44%,
            78% 52%,
            65% 64%,
            56% 82%,
            54% 100%,
            19% 100%
          );
          height: 30px;
          width: 30px;
          left: -10px;
          top: -10px;
        }
        &.third:after {
          content: "";
          position: absolute;
          background-color: $background_3;
          clip-path: polygon(
            22% 69%,
            37% 43%,
            62% 23%,
            100% 12%,
            100% 44%,
            78% 52%,
            65% 64%,
            56% 82%,
            54% 100%,
            19% 100%
          );
          height: 30px;
          width: 30px;
          left: -10px;
          top: -10px;
        }
        &.third:before {
          content: "";
          position: absolute;
          background-color: $background_3;
          clip-path: polygon(
            22% 69%,
            37% 43%,
            62% 23%,
            100% 12%,
            100% 44%,
            78% 52%,
            65% 64%,
            56% 82%,
            54% 100%,
            19% 100%
          );
          transform: rotate(-90deg) scale(1.1);
          height: 30px;
          width: 30px;
          left: -10px;
          bottom: -9px;
        }
      }
    }
  }

  &__code {
    &-item {
      span {
        float: right;
        color: $white_para;
      }
      .bar {
        width: 100%;
        height: 4px;
        border-radius: 1px;
        margin: 7px 0 10px 0;
        background-color: $background_4;

        &-item {
          height: 100%;
          border-radius: 1px;
          background-color: $yellow;

          &.first {
            width: 90%;
          }
          &.second {
            width: 70%;
          }
          &.third {
            width: 70%;
          }
          &.fourth {
            width: 50%;
          }
          &.fifth {
            width: 40%;
          }
        }
      }
    }
  }

  &__knowledge {
    h5 {
      color: $white_para;
    }
    i {
      color: $yellow;
      margin-right: 20px;
    }
  }

  &__cv {
    font-weight: 700;
    font-size: 1rem;

    a {
      cursor: pointer;
      transition: color 0.3s;

      &:hover {
        color: $white_heading;
      }
    }

    i {
      margin-left: 10px;
    }
  }
}

.footer {
  position: fixed;
  bottom: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 280px;
  height: 50px;
  background-color: $background_2;

  i {
    font-size: 1.3rem;
    margin: 0 15px;
    transition: color 0.3s;

    &:hover {
      color: $white_heading;
    }
  }
}

/********** Main **********/

.container {
  background-color: $background_1;
  transition: all .4s;
  margin-right: 80px; 

  &.open {
    position: relative;
    transform: translateX(-120px);
    opacity: .3;
    z-index: -10000;

  }
}

/********** Right Aside **********/

.right-aside {
  background-color: $background_3;
  position: fixed;
  top: 0;
  bottom: 0;
  right: 0;
  width: 200px;
  transform: translateX(120px);
  transition: transform 0.3s;

  .top {
    height: 80px;
    background-color: $background_2;
    position: relative;

    &__container {
      position: absolute;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      height: 15px;
      width: 30px;
      top: 50%;
      left: 30px;
      cursor: pointer;

      &-item {
        width: 20px;
        height: 3px;
        border-radius: 2px;
        background-color: $yellow;
        opacity: 0.5;
        transition: all 0.3s;
      }
      &:hover .top__container-item {
        opacity: 1;
      }
    }
  }

  .nav {
    padding: 20px 0 0 20px;

    &__item {
      margin: 10px 0;
      cursor: pointer;
      font-size: 1.02rem;
      font-weight: 500;
      opacity: 0;
      transition: transform 0.6s, opacity 0.6s, color 0.3s;

      &:nth-child(1) {
        transform: translateX(400px);
      }

      &:nth-child(2) {
        transform: translateX(300px);
      }

      &:nth-child(3) {
        transform: translateX(200px);
      }

      &:nth-child(4) {
        transform: translateX(100px);
      }
    }
  }

  &.open {
    transform: translateX(0);

    .top__container {
      &-item:nth-child(1) {
        transform: rotate(45deg) translateY(3px) translateX(5px);
        height: 4px;
        opacity: 1;


      }
      &-item:nth-child(2) {
        opacity: 0;
      }
      &-item:nth-child(3) {
        transform: rotate(-45deg) translateY(-3px) translateX(5px);
        height: 4px;
        opacity: 1;

      }
    }

    .nav__item {
      opacity: 1;
      transform: translateX(0);

      &:hover {
        color: $white_heading;
      }
    }
  }
}
</style>

<aside class="right-aside">
  <div class="top">
    <div class="top__container">
      <div class="top__container-item"></div>
      <div class="top__container-item"></div>
      <div class="top__container-item"></div>
    </div>
  </div>
  <nav class="nav">
    <ul>
      <li class="nav__item">Présentation</li>
      <li class="nav__item">Compétences</li>
      <li class="nav__item">Templates</li>
      <li class="nav__item">Contact</li>
    </ul>
  </nav>
</aside>