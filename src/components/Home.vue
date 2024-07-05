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
  <div class="container mt-5">
    <span>Explore mais </span>
    <h2 class="mb-4">Outras opções para você</h2>
    <div class="row justify-content-md-center">
      <div v-for="(image, index) in images" :key="index" class="col-md-3">
        <img :src="image" :alt="'Imagem ' + (index + 1)" class="image-card" />
      </div>
    </div>
    
  </div>
  <Disponivel />
  <visitados />

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
      images: [
        "../src/assets/fut.png",
        "../src/assets/Pessoas.png",
        "../src/assets/escravidaoexp.png",
        "../src/assets/culturalExp.png",
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
  flex-direction: column;
}

.card-tag {
  background-repeat: no-repeat;
  background-size: cover;
}


.input-overlay {
  position: absolute;
  top: 73%;
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
  top: 73%;
  left: 65%;
  transform: translate(-50%, -50%);
}

img {
  width: 100%;
}
</style>
