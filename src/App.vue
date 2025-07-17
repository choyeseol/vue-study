<template>
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
        <button @click="isModal=true">상세보기</button>
      </p>
    </div>
  </div>

  <div class="modal" v-if="isModal">
    <div class="inner">
      <h3>Detail</h3>
      <p>영화 상세정보</p>
      <button @click="isModal=false">닫기</button>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'App',
    data() {
      return {
        isModal: false,
        foods: ['김밥', '순대', '만두'],
        data: [
          {
            title: '노량',
            year: 2021,
            category: '액션, 드라마',
            textRed: 'color: red',
            like: 0,
            imgUrl: '/assets/cat.jpeg'
          },
          {
            title: '아쿠아맨',
            year: 2022,
            category: '액션, 판타지, 어드밴처',
            like: 0,
            imgUrl: '/assets/seol.jpeg'
          },
          {
            title: '3일의 휴가',
            year: 2023,
            category: '판타지, 드라마',
            like: 0,
            imgUrl: '/assets/sol.JPG'
          }
        ]
      }
    },
    methods: {
      increaseLike(i) {
        this.data[i].like += 1;
      }
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
