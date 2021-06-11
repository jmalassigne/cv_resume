<template>
  <div>
    <div class="component__container">
      <h4 class="title">Mes services</h4>
      <div class="services">
        <div class="services__card">
          <h6 class="services__card-title">Développement frontend</h6>
          <p>
            Lorem ipsum dolor sit, amet consectetur adipisicing elit. Nam
            explicabo dolorum, laborum est ullam pariatur necessitatibus aliquid
            saepe consequuntur, iusto accusamus earum, molestiae omnis.
            Accusantium id magni incidunt illum facilis iste, mollitia
            distinctio ullam excepturi libero quo culpa tempore porro adipisci?
            Facilis et quis suscipit, officiis vero sint amet odio.
          </p>
        </div>
        <div class="services__card">
          <h6 class="services__card-title">Développement backend</h6>
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Corporis
            non, rem quod saepe itaque optio. Tempore molestias adipisci
            aspernatur ipsam delectus dolor aut. Tempore ex sint magni totam
            consectetur, non velit quibusdam commodi quisquam culpa
            necessitatibus ab odio veniam molestiae ratione harum nulla labore
            porro aperiam nemo rem. Nisi, itaque!
          </p>
        </div>
        <div class="services__card">
          <h6 class="services__card-title">Maintenance</h6>
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Eligendi
            magni ut unde nesciunt doloremque hic voluptatibus aliquid totam
            tempora. Aspernatur, reiciendis consectetur? Modi quisquam
            reprehenderit quaerat accusamus ducimus esse ab, perferendis quae
            eveniet magnam, quas provident delectus, doloribus odit quasi
            dolorum nostrum ullam sunt blanditiis adipisci tenetur similique
            animi. Pariatur.
          </p>
        </div>
      </div>
      <h4 class="title">Mes connaissances</h4>
      <div class="knowledge">
        <div class="knowledge__card">
          <h5>Frontend</h5>
          <div class="knowledge__card-item">
            <h6>HTML</h6>
            <div class="progressBar">
              <div class="progressBar-content" style="width: 80%"></div>
            </div>
          </div>
          <div class="knowledge__card-item">
            <h6>CSS</h6>
            <div class="progressBar">
              <div class="progressBar-content" style="width: 70%"></div>
            </div>
          </div>
          <div class="knowledge__card-item">
            <h6>JavaScript</h6>
            <div class="progressBar">
              <div class="progressBar-content" style="width: 70%"></div>
            </div>
          </div>
          <div class="knowledge__card-item">
            <h6>VueJs</h6>
            <div class="progressBar">
              <div class="progressBar-content" style="width: 75%"></div>
            </div>
          </div>
        </div>
        <div class="knowledge__card">
          <h5>Backend</h5>
          <div class="knowledge__card-item">
            <h6>NodeJS</h6>
            <div class="progressBar">
              <div class="progressBar-content" style="width: 50%"></div>
            </div>
          </div>
          <div class="knowledge__card-item">
            <h6>PHP</h6>
            <div class="progressBar">
              <div class="progressBar-content" style="width: 50%"></div>
            </div>
          </div>
          <div class="knowledge__card-item">
            <h6>MySQL</h6>
            <div class="progressBar">
              <div class="progressBar-content" style="width: 70%"></div>
            </div>
          </div>
          <div class="knowledge__card-item">
            <h6>SQLite</h6>
            <div class="progressBar">
              <div class="progressBar-content" style="width: 80%"></div>
            </div>
          </div>
        </div>
        <div class="knowledge__card">
          <h5>Autres</h5>
          <div class="knowledge__card-item">
            <h6>Wordpress</h6>
            <div class="progressBar">
              <div class="progressBar-content" style="width: 40%"></div>
            </div>
          </div>
          <div class="knowledge__card-item">
            <h6>Github</h6>
            <div class="progressBar">
              <div class="progressBar-content" style="width: 80%"></div>
            </div>
          </div>
          <div class="knowledge__card-item">
            <h6>SEO</h6>
            <div class="progressBar">
              <div class="progressBar-content" style="width: 70%"></div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Skills",
};
</script>

<style lang="scss" scoped>
@import "../styles/_variables.scss";

.component__container {
  width: 90%;
  margin: 50px auto;
  background: none;
}

.title {
  font-size: 1.2rem;
  margin: 30px 0;
}

.services {
  width: 100%;
  display: flex;
  justify-content: space-between;
  
  @media (max-width: 1100px) {
    flex-direction: column;
  }

  &__card {
    width: 300px;
    background: $background_4;
    border-radius: 5px;
    padding: 10px;
    
    @media (max-width: 1480px) {
    width: 270px;
  }

  @media (max-width: 1350px) {
    width: 240px;
  }

    @media (max-width: 1260px) {
    width: 200px;
  }

  @media (max-width: 1100px) {
    width: 100%;
    margin-bottom: 10px;
  }

    &-title {
      font-weight: 600;
      font-size: 1.05rem;
      text-align: center;
      margin-bottom: 5px;
    }
  }
}

.knowledge {
  display: flex;
  flex-wrap: wrap;
  width: 100%;
  padding: 30px;
  background: $background_4;
  border-radius: 5px;

  &__card {
    width: 50%;

    h5 {
      margin: 10px 0;
      color: $white_heading;
      font-size: 1.02rem;
    }

    &-item {
      h6 {
        color: $white_para;
      }

      .progressBar {

        width: 70%;
        height: 5px;
        margin: 5px 0 10px 0;
        background: $background_1;
        border-radius: 1px;

        &-content {
          background: $yellow;
          height: 100%;
        }
      }
    }
  }
}
</style>