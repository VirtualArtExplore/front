<template>
  <div class="container">
  <span>Explore mais </span>
  <h2 class="mb-4">Outras opcões para você</h2>
  <div class="row">
    <div v-for="(image, index) in images" :key="index" class="col-md-4 mb-4">
      <div class="card-container">
        <div class="card-overlay ">
          <div class="row justify-content-md-center">
            <div class="col-md-3">
              <img
                :src="image"
                :alt="'Imagem ' + (index + 1)"
                class="card-img-top img"
              />
            </div>
            <div class="col-md-9">
              <div class="content">
                <h5 class="card-title">Charles V, bust length...</h5>
                <span>Maceió, Alagoaso</span>
                <strong>29/03/2024 - 01/06/2024</strong>
              </div>
            </div>
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
      "../src/assets/geovane.png",
      "../src/assets/image2.png",
      "../src/assets/Group95.png",
    ],
    favorites: [], // Array para rastrear quais itens são favoritos
  };
},
methods: {
  toggleFavorite(index) {
    if (this.isFavorite(index)) {
      // Se já for favorito, remover da lista de favoritos
      this.favorites.splice(this.favorites.indexOf(index), 1);
    } else {
      // Se não for favorito, adicionar à lista de favoritos
      this.favorites.push(index);
    }
  },
  isFavorite(index) {
    // Verificar se o item está na lista de favoritos
    return this.favorites.includes(index);
  },
},
components: {
  FontAwesomeIcon,
},
};
</script>

<style scoped>
.card-container {
}

.card-overlay {
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

.img {
width: 100%;
overflow: hidden;
border-radius: 5px;
}
</style>