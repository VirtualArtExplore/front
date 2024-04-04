<template>
  <div class="py-5 mt-5 container">
    <span> Tópicos para você </span>
    <h2 class="">Mais visitados</h2>
    <div class="row">
      <!-- Use o loop apenas para as imagens -->
      <div v-for="(image, index) in images" :key="index" class="col-md-4 mt-4 mb-5">
        <div class="card-container position-relative">
          <div class="img">
            <img
              :src="image"
              :alt="'Imagem ' + (index + 1)"
              class="card-img-top"
            />
          </div>
          <div class="card-overlay">
            <div class="content">
              <h5 class="card-title">Museu Théo Brandão</h5>
              <span>Maceió, Alagoas</span>
              <strong>Público</strong>
            </div>
            <div class="content">
              <FontAwesomeIcon :icon="faHouse" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import { faHouse } from "@fortawesome/free-solid-svg-icons";

export default {
  data() {
    return {
      images: [
        "../src/assets/teoBrandao.png",
        "../src/assets/floriano.png",
        "../src/assets/image1.png",
        "../src/assets/noname.png",
        "../src/assets/palacio.png",
        "../src/assets/museu-1.png",
      ],
    };
  },
  components: {
    FontAwesomeIcon,
  },
};
</script>

<style scoped>
.card-container {
  position: relative;
}

.card-overlay {
  position: absolute;
  top: 97%;
  left: 47%;
  transform: translate(-50%, -50%);
  width: 80%; /* Ajuste conforme necessário */
  background-color: rgba(255, 255, 255, 1);
  padding: 1rem;
  border-radius: 17px;
  z-index: 1;
}

.card-title {
  margin-bottom: 0.5rem;
}

.content {
  display: flex;
  flex-direction: column; 
}

.card-text {
  margin-bottom: 1rem;
}

.fa-heart {
  cursor: pointer;
}

.fa-heart.fas {
  color: yellow;
}

.img {
  width: 100%;
  overflow: hidden;
  border-radius: 17px;
}

.card-img-top {
  width: 100%;
  height: auto;
  display: block;
  max-width: 391px;
}
</style>
