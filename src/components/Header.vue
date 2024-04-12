<template>
  <div class="container py-4">
    <div class="row align-items-center">
      <div class="col-md-2 pb-4">
        <a href="http://">Favoritos</a>
      </div>
      <div class="col-md-3 pb-4">
        <img src="../assets/museum-logo.png" alt="" class="logo" />
      </div>
      <div class="col-md-1 pb-4">
        <a href="./LoginModal.vue">Entrar</a>
      </div>
      <div class="col-md-1 pb-4">
        <a href="http://">Registrar</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  methods: {
    scrollToTop() {
      window.scrollTo({
        top: 0,
        behavior: "smooth",
      });
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
}
</style>
