<template>
  <div class="mt-5 container p-0" style="width: 100%;">
    <span class="subtitle" > Tópicos para você </span>
    <h2 class="title-h2">Mais visitados</h2>
    <div class="grid">
      <div
      v-for="item in items" :key="item.id"
        class="box-1"
      >
        <div class="card-container position-relative">
          <div class="img">
            <img
              :src="item.thumbnail"
              :alt="'Imagem ' + item.title"
              class="card-img-top"
            />
          </div>
          <div class="card-overlay d-flex d-row align-items-center justify-content-center">
            <div class="content">
              <h5 class="card-title">{{ item.title }}</h5>
              <span class="text-location">Maceió-AL</span><span>{{ item.category }}</span>

            </div>
            <div class="">
              <img class="icon" src="@/assets/Icons.png" alt="Icons" />
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="row justify-content-center mt-5">
      <!--<button type="button" class="btn btn-warning w-25 mb-4">
        Mais Museus
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512" fill="white" width="20px"><path d="M438.6 278.6c12.5-12.5 12.5-32.8 0-45.3l-160-160c-12.5-12.5-32.8-12.5-45.3 0s-12.5 32.8 0 45.3L338.8 224 32 224c-17.7 0-32 14.3-32 32s14.3 32 32 32l306.7 0L233.4 393.4c-12.5 12.5-12.5 32.8 0 45.3s32.8 12.5 45.3 0l160-160z"/></svg>

      </button>-->
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      items: [],
      currentPage: 1,
      itemsPerPage: 4,  
      totalPages: 0
  }},
  mounted(){
  this.fetchData();;
},
methods: {
  async fetchData() {
    const url = `https://dummyjson.com/products?limit=30`
      const response = await axios.get(url); // Substitua pela sua URL
      this.items = response.data.products.filter(item => item.category === 'beauty');
    }
},
};
</script>

<style scoped>
.grid{
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  flex-direction: row;
}
.box-1{
  width: 25%;
  display: flex;
  justify-content: center;
  max-width: 400px;
  min-width: 200px;
}
.card-container {
  position: relative;
  width: 90%;
  margin-bottom: 100px;
}

.card-overlay {
  position: absolute;
  margin-top: -50px;
  width: 100%; /* Ajuste conforme necessário */
  background-color: rgba(255, 255, 255, 1);
  padding: 10px;
  border-radius: 16px;
  z-index: 5;
  color: var(--vt-c-brown);
  font-family: 'poppins';
  box-shadow: 0px 0px 50px rgba(0, 0, 0, 0.4);
}

.card-title {
  margin-bottom: 0.4rem;
  font-size: 1rem;
  font-weight: 600;
}

.content {
  display: flex;
  flex-direction: column;
  width: 100%;
}

.card-text {
  margin-bottom: 1rem;
}

.fa-heart {
  cursor: pointer;
}

.text-location{
  font-weight: 500;
  font-size: 14px;
  color: var(--vt-c-brown);
  opacity: 0.5;
}

.img {
  width: 100%;
  overflow: hidden;
  border-radius: 15px;
  object-fit: contain;
}

.btn {
  background-color: var(--vt-c-orange);
  font-family: 'poppins';
  font-weight: 600;
  color: #fff;
  font-size: 20px;
  border: none;
  height: 60px;
  max-width: 220px;
}
.btn:hover {
  background-color: var(--vt-c-brown);
  color: #fff;
  transform: scale(1.02);
  transition: 0.3s;
}
.card-img-top {
  width: 100%;
  height: 250px;
  display: block;
}
.icon {
  width: 40px;
  height: auto;
}


@media screen and (max-width: 768px) {
  .box-1 {
    width: 100%;
  }
  .card-overlay{
    width: 80%;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
  }
  .grid{
    justify-content: center;
  }

}
</style>
