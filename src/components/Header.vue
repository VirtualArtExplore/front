<template>
  <div class="container py-4 z-20">
    <div class="row align-items-center">
      <div class="col-md-2 pb-4">
        <a href="http://">Favoritos</a>
      </div>
      <div class="col-md-3 pb-4">
        <img src="../assets/museum-logo.png" alt="" class="logo" />
      </div>
      <div class="col-md-1 pb-4">
        <a v-on:click="openLogin">Entrar</a>
        <LoginModal v-if="loginActive" @closeLog="closeLogin"/>
      </div>
      <div class="col-md-1 pb-4">
        <a v-on:click="openRegister">Registrar</a>
        <RegisterModal v-if="registerActive" @closeReg="closeRegister"/>
      </div>
    </div>
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
.container {
  position: absolute;
  bottom: 79%;
  left: 29%;
}
img {
  width: 100%;
}

.logo {
  width: 100%;
  max-width: 208px;
}
.arrow {
  max-width: 40px;
}

.code {
  max-width: 24px;
}

a {
  color: white;
  font-family: "Poppins", sans-serif;
  cursor: pointer;
}
</style>
