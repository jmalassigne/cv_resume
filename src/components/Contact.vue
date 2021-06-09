<template>
  <div class="component__container">
    <div class="infos">
      <div class="infos__card">
        <h5 class="infos__card-title">Informations</h5>
        <p>
          <i class="far fa-flag"></i>Pays: <span class="float">France</span>
        </p>
        <p>
          <i class="far fa-building"></i>Ville:
          <span class="float">Saint-brieuc</span>
        </p>
        <p>
          <i class="far fa-clock"></i>Age: <span class="float">29 ans</span>
        </p>
      </div>
      <div class="infos__bar"></div>
      <div class="infos__card">
        <p>
          <i class="far fa-envelope"></i>Mail:
          <span class="float"
            ><a href="mailto: j.malassigne22@gmail.com"
              >j.malassigne22@gmail.com</a
            ></span
          >
        </p>
        <p>
          <i class="fas fa-phone"></i>Telephone:
          <span class="float"
            ><a href="tel: 0661210456">06 61 21 04 56</a></span
          >
        </p>
        <p>
          <i class="fab fa-linkedin"></i>Linkedin:
          <span class="float"><a href="/j.malassigne">/j.malassigne</a></span>
        </p>
        <p>
          <i class="fab fa-github"></i>Github:
          <span class="float"><a href="/j.malassigne">/j.malassigne</a></span>
        </p>
      </div>
    </div>
    <div class="contact">
      <h5 class="contact__title">Me contacter</h5>
      <form class="form" action="">
        <div class="input-container">
          <div class="i">
            <i class="fas fa-user"></i>
          </div>
           <input class="input" type="text" placeholder="Votre nom">
        </div>
        <div class="input-container">
          <div class="i">
            @
          </div>
          <input class="input" type="mail" placeholder="Votre adresse mail">
        </div>
        <div class="input-container">
        <div class="i">
          <i class="fas fa-envelope-open"></i>
        </div>
        <textarea class="textarea" name="" placeholder="Votre message"></textarea>
        </div> 
        <button class="submit" type="submit">Envoyer</button>       
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "Contact",
};
</script>

<style lang="scss" scoped>
@import "../styles/_variables.scss";

.component__container {
  width: 90%;
  margin: 50px auto;
  background: none;
}

.infos {
  padding: 20px;
  width: 100%;
  display: flex;
  justify-content: space-between;
  background: $background_4;
  border-radius: 10px;

  &__card {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    width: 40%;
    margin: 0;
    color: $white_heading;

    &-title {
      font-size: 1.1rem;
      margin: 5px 0;
    }

    p {
      margin: 5px 0;
    }

    span {
      float: right;
      color: $white_para;
    }

    i {
      margin-right: 10px;
      color: $yellow;
    }

    a {
      transition: color .3s;

      &:hover {
        color: $yellow;
        text-decoration: underline;
      }
    }
  }

  &__bar {
    width: 2px;
    flex-basis: 1;
    background: $white_para;
  }
}

.contact {
  width: 100%;
  padding: 40px;
  margin-top: 60px;
  background: $background_4;

  &__title {
    font-size: 1.1rem;
  }

  form {
    display: flex;
    flex-direction: column;

    .input-container {
      display: flex;
      margin: 10px 0;

      &:first-child {
        height: 40px;
      }

       &:nth-child(2) {
        height: 40px
      }

       &:last-child {
        height: 80px;
      }

      .i {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 5%;
        background: $background_1;
      }
    }

    .input, .textarea {
      display: inline-block;
      width: 95%;
      background: $background_2;
      margin: 10px 0;
      border-radius: 0 20px 20px 0;
      border: none;
      height: 100%;
      margin: 0;
      color: white;

      &:focus {
        outline: none;
        box-shadow: 2px 2px $yellow, -2px 2px $yellow, 2px -2px $yellow, -2px -2px $yellow
      }
    }

    .textarea {
      height: 100px;
      font-family: 'poppins', sans-serif;
      vertical-align: middle;
    }
    .submit {
      cursor: pointer;
      color: black;
      width: 100px;
      height: 40px;
      border-radius: 5px;
      border: none;
      background: $yellow;
      margin: 10px auto;
    }
  }
}

</style>