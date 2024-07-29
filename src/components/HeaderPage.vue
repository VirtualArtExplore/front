<template>
    <div class="fundo d-flex flex-row align-items-center justify-content-around align-items-baseline py-3">
      <div class="">
        <ul class="d-flex flex-row p-0">
          <li><a href="">Museus</a></li>
          <li><a class="px-2" href="">Obras</a></li>
          <li><a href="">Exposições</a></li>
        </ul>
      </div>
      <div class="">
        <img src="../assets/logo-virtual-marrom.png" alt="" class="logo" />
      </div><!--
      <div class="d-flex flex-row p-0 ">
        <a class="btn mx-3" v-on:click="openLogin">Entrar</a>
        <LoginModal v-if="loginActive" @closeLog="closeLogin"/>
        <a class="btn mx-2 btn-outline-light register" v-on:click="openRegister">Registrar</a>
        <RegisterModal v-if="registerActive" @closeReg="closeRegister"/>
      </div>-->
    </div>
</template>

<script>
import LoginModal from "./LoginModal.vue";
import RegisterModal from "./RegisterModal.vue";

export default {
  components: { LoginModal,RegisterModal },
  data() {
    return {
      loginActive: false,
      registerActive: false,
    };
  },
  methods: {
    scrollToTop() {
      window.scrollTo({
        top: 0,
        behavior: "smooth",
      });
    },
    openLogin() {
      this.loginActive = true;
    },
    closeLogin() {
      this.loginActive = false;
    },
    openRegister() {
      this.registerActive = true;
    },
    closeRegister() {
      this.registerActive = false;
    },
  },
};
</script>

<style scoped>
.fundo {
  position: relative;
  background-color: var(--vt-c-header);
  width: 99%;
  z-index: 20;
}
.logo {
  width: 100%;
  max-width: 180px;
}
.arrow {
  max-width: 40px;
}
.code {
  max-width: 24px;
}
a {
  color: var(--vt-c-brown);
  font-family: "Poppins", sans-serif;
  cursor: pointer;
  font-size: 1rem;
}
ul{
  list-style: none;
}
.btn.mx-2.btn-outline-light.register{
  border: solid 1px var(--vt-c-brown);
}
</style>
