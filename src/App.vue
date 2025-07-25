<template>
  <Navbar />
  <Event :text="text" />
  <Movies 
  :data="data"
  @openModal="isModal=true; selectedMovie=$event"
  @increaseLike="increaseLike($event)"/>
  <Modal 
    :data="data"
    :isModal="isModal"
    :selectedMovie="selectedMovie"
    @closeModal="isModal=false"
  />
</template>

<script>
import data from './assets/movies'
import Modal from './components/Modal.vue';
import Navbar from './components/Navbar.vue';
import Event from './components/Event.vue';
import Movies from './components/Movies.vue';

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
    Event: Event,
    Movies: Movies
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
