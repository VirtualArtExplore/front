<template>
  <div class="container py-4">
    <div class="row align-items-center">
      <div class="col-md-9 pb-4">
        <img src="../assets/museum.png" alt="" class="logo" />
      </div>
      <div class="col-md-2 pb-4">
        <button @click="scrollToTop" class="btn">
          <img src="../assets/ArrowCircleUp.png" alt="" class="arrow" />
          Voltar ao topo
        </button>
      </div>
      <hr>
      <div class="col-md-9 ">
        ©2024
      </div>
      <div class="col-md-3 ">
        <img src="../assets/code.png" alt="" class="code">
        Desenvolvido por <span> Gustavo Ataide </span>
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
        behavior: "smooth" 
      });
    }
  }
};
</script>

<style scoped>
.container {
  font-family: "Poppins", sans-serif;
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
</style>
