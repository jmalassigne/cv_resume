<template>
  <div id="app">
    <div v-if="isLoading">
      <div class="loading">
        <h1 class="loading__heading">julien malassigne</h1>
        <div class="loading__bar">
          <div class="loading__bar-item" :class="{start: startProgress}"></div>
        </div>
        <p>{{progress}} %</p>
      </div>
    </div>
    <div v-else class="main-page">
      <aside class="aside-left">

      </aside>
      <Prez/>
      <aside class="aside-right">
        
      </aside>
    </div>
  </div>
</template>

<script>
import Prez from './components/Prez.vue'

export default {
  name: 'App',
  components: {
    Prez
  },
  data() {
    return {
      isLoading: true,
      startProgress: false,
      progress: 0
    }
  },
  mounted() {
    setTimeout(() => {
      this.startProgress = true;
    }, 500);

    setInterval(() => {
      if(this.progress < 100){
        this.progress++;
      }
      }, 20);

    setTimeout(() => {
      this.isLoading = !this.isLoading;
    }, 3000);
  }
}
</script>

<style lang='scss'>

@import './styles/_variables.scss';

/********** Reset **********/  

html,body,p,ol,ul,li,dl,dt,dd,blockquote,figure,fieldset,legend,textarea,pre,iframe,hr,h1,h2,h3,h4,h5,h6{margin:0;padding:0}h1,h2,h3,h4,h5,h6{font-size:100%;font-weight:normal}ul{list-style:none}button,input,select{margin:0}html{box-sizing:border-box}*,*::before,*::after{box-sizing:inherit}img,video{height:auto;max-width:100%}iframe{border:0}table{border-collapse:collapse;border-spacing:0}td,th{padding:0}

/********** Global styles **********/ 

html {
  background-color: $background_1;
}

body {
  color: $white_para;
  font-size: 16px;
  font-weight: 500;
  padding: 20px 0;
}

h1,h2,h3,h4,h5,h6 {
  color: $white_heading;
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
  max-width: 300px;
  margin-left: auto;
  margin-right: auto;
}

</style>
