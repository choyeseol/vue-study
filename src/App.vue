<template>
  <Navbar />
  <Event :text="text" />
  <h1>영화 정보</h1>
  <div v-for="(movie, i) in data" :key = "i" class="item">
    <figure>
      <img :src="`${movie.imgUrl}`" :alt="`${movie.title}`">
    </figure>
    <div class="info">
      <h3 classstyle="textRed">{{ movie.title }}</h3>
      <p> {{ movie.year }}</p>
      <p>{{ movie.category }}</p>
      <button @:click="increaseLike(i)">좋아요</button> <span>{{ movie.like }}</span>
      <p>
        <button @click="isModal=true; selectedMovie = i">상세보기</button>
      </p>
    </div>
  </div>
  <Modal />
</template>

<script>
import data from './assets/movies'
import Modal from './components/Modal.vue';
import Navbar from './components/Navbar.vue';
import Event from './components/Event.vue';

export default {
  name: 'App',
  data() {
    return {
      isModal: false,
      data: data,
      selectedMovie: 0,
      text: "NEPLIX 강렬한 운명의 드라마, 경성크리처"
    }
  },
  methods: {
    increaseLike(i) {
      this.data[i].like += 1;
    }
  },
  components: {
    Navbar: Navbar,
    Modal: Modal,
    Event: Event
  }
}

</script>

<style>
  .bg-yellow {
    background-color: yellow;
    padding: 10px;
  }

  * {
    box-sizing: border-box;
    margin: 0;
  }

  body {
    padding: 20px;
    margin:  0 auto;
    max-width: 768;
  }

  h1, h2, h3 {
    margin-bottom: 1rem;
  }

  p {
    margin-bottom: 0.5rem;
  }

  button {
    margin-right: 10px;
    margin-top: 1rem;
  }

  .item {
    border: 1px solid #ccc;
    width: 100%;
    padding: 1rem;
    margin-bottom: 20px;
    display: flex;
  }

  .item figure {
    margin-right: 1rem;
    width: 30%;
  }

  .item img {
    width: 100%;
  }

  .item .info{
    width: 100%;
  }

  .modal {
    align-items: center;
    justify-content: center;
    display: flex;
    height: 100vh;
    width: 100%;
    top: 0;
    left: 0;
    position: fixed;
    background: rgb(0, 0, 0, 0.5);
  }

  .modal .inner {
    border-radius: 10px;
    padding: 20px;
    width: 80%;
    background: white;
  }
</style>
