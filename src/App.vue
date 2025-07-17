<template>
  <h1>영화 정보</h1>
  <div v-for="(movie, i) in data" :key = "i">
    <h3 class="bg-yellow" :style="textRed">{{ movie.title }}</h3>
    <p> {{ movie.year }}</p>
    <p>{{ movie.category }}</p>
  </div>
  <!-- 
  <p>{{ foods[0] }}</p>
  <p>{{ foods[1] }}</p>
  <p>{{ foods[2] }}</p> 
  -->
  <p v-for="(item, i) in foods" :key = "i">{{ item }}</p>
</template>

<script>
  export default {
    name: 'App',
    data() {
      return {
        foods: ['김밥', '순대', '만두'],
        data: [
          {
            title: '노량',
            year: 2021,
            category: '액션, 드라마',
            textRed: 'color: red'
          },
          {
            title: '아쿠아맨',
            year: 2022,
            category: '액션, 판타지, 어드밴처'
          },
          {
            title: '3일의 휴가',
            year: 2023,
            category: '판타지, 드라마'
          }
        ]
      }
    }
  }

</script>

<style>
  .bg-yellow {
    background-color: yellow;
    padding: 10px;
  }
</style>
