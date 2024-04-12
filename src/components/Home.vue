<template>
  <LoginModal/>
  <div class="image-container">
    <Header></Header>
    <img src="../assets/ImageHero.png" alt="Imagem" class="image" />
    <h1 class="image-text">
      Tenha Uma Incrível <br />
      <span> Experiência </span> Aqui!
    </h1>
    <input
      type="text"
      class="input-overlay"
      placeholder="Procure por Museu, Cidade, Estado...."
    />
    <font-awesome-icon icon="search" class="search-icon" size="lg"/>
  </div>
  <visitados />
  <Disponivel />
  <Footer></Footer>

</template>
<script>
import Visitados from "./Visitados.vue";
import Disponivel from "./Disponivel.vue";
import Footer from "./Footer.vue";
import Header from "./Header.vue";
import LoginModal from "./LoginModal.vue";


export default {
  components: { Visitados,Disponivel,Footer,Header,LoginModal},
  data() {
    return {};
  },
};
</script>

<style>
.image-container {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
}

.input-overlay {
  position: absolute;
  top: 74%;
  left: 49%;
  transform: translate(-50%, -50%);
  padding: 13px 14px;
  border: 1px solid #ccc;
  border-radius: 18px;
  opacity: 0.8;
  text-align: start;
  width: 100%;
  max-width: 773px;
  height: 71px;
  font-size: 17px;
}

.image-text {
  position: absolute;
  top: 36%;
  left: 32%;
  color: white;
  text-align: center;
  font-size: 65px;
  font-weight: bold;
  font-family: "Poppins", sans-serif;
}

span {
  font-weight: bold;
  font-family: "Poppins", sans-serif;
  color: #e0a449;
}

.search-icon {
  position: absolute;
  top: 74%;
    left: 65%;
  transform: translate(-50%, -50%);
}

img {
  width: 100%;
}
</style>
