<template>
  <Header></Header>

  <div class="image-container">

<div class="input-div"><input
      type="text" class="input-overlay"
      placeholder="Procure por Museu, Cidade, Estado...."
    />
    <button class="button-search"><font-awesome-icon icon="search" class="search-icon" size="lg" /></button>
</div>
  </div>

    <visitados />

  <!--<Disponivel />-->

  <Footer></Footer>
</template>
<script>
import Visitados from "./Visitados.vue";
import Disponivel from "./Disponivel.vue";
import Footer from "./Footer.vue";
import Header from "./HeaderPage.vue";

export default {
  components: { Visitados, Disponivel, Footer, Header },
  data() {
    return {
    };
  },
};
</script>

<style>
.categ-title{
  font-family: 'Poppins';
  color: white;
  font-size: 1.5rem;
  text-align: center;
}
.image-container {
  padding-top: 0px;
  background-image: url("../assets/categorias/capa-museu2.jpg");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  height: 100px;
}
.card-tag {
  background-repeat: no-repeat;
  background-size: cover;
}
.button-search{
  width:10%;
  border:none;
  background-color: rgba(0, 0, 0, 0);
}
.input-div{
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  border: none;
  border-radius: 15px;
  background-color: #E9E9E9;
  max-width: 1300px;
  width: 90%;
}
.input-overlay {
  position: relative;
  padding: 18px 10px;
  text-align: start;
  border: none;
  width: 100%;
  max-width: 700px;
  font-size: 1.1rem;
  font-family: "Poppins", sans-serif;
  background-color: rgba(0, 0, 0, 0);
  width: 90%;
  color: #000;
  font-weight: 500;
}

.image-text {
  position: relative;
  color: white;
  text-align: center;
  font-size: 3.5rem;
  font-weight: bold;
  font-family: "Poppins", sans-serif;
}

span {
  font-weight: bold;
  font-family: "Poppins", sans-serif;
  color: var(--vt-c-orange);
}

.search-icon {
  position: relative;
}

img {
  width: 100%;
}
textarea:focus, input:focus, select:focus {
    box-shadow: 0 0 0 0;
    border: 0 none;
    outline: 0;
}

@media screen and (max-width: 768px) {
  .image-text {
    font-size: 2.5rem;
  }
  .category{
    width: 100%;
    height: 70px;
    border-radius: 10px;
    margin-top: 5px;
  }

}
</style>
