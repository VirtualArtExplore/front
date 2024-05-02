<template>
  <Header></Header>

  <div class="image-container">
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
    <font-awesome-icon icon="search" class="search-icon" size="lg" />
  </div>
  <div class="container categorias mt-5">
    <h1 class="">
      Encontre pelo seu gosto <br />
      <span> Categorias </span>
    </h1>
      <div class="cards">
        <div class="categoria" v-for="(categoria, index) in categorias" :key="index">
          <img :src="categoria":alt="'Imagem ' + (index + 1)"
              class="img-card">

        </div>
      </div>
      <div class="content">
        <FontAwesomeIcon :icon="faHouse" />
      </div>
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

export default {
  components: { Visitados, Disponivel, Footer, Header },
  data() {
    return {
      categorias: [
        "../src/assets/categorias/esp.png",
        "../src/assets/categorias/pessoas.png",
        "../src/assets/categorias/escravidao.png",
        "../src/assets/categorias/culturaLocal.png"
      ],
    };
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
.cards {
  width: 100%;
  background-size: contain;
  background-repeat: no-repeat;
  background-color: transparent;
  display: flex;
  justify-content: flex-end;
}
</style>
