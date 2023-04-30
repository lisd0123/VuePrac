<template>
  <div class = "menu">
    <a v-for="a in 메뉴들" :key="a">{{ a }}</a>
    
  </div>

  <!-- <div v-for="(a,i) in products" :key="i">
    <h4 >{{ a }}</h4>
  </div> -->

  <div>
    <h4 class="red" :style="스타일">{{products[0]}}</h4>
    <p>{{ price1 }} 만원</p>
    <button @click="increase(0)">허위매물신고</button> <span>신고수 : {{신고수[0]}}</span>
  </div>
  <div>
    <h4>{{products[1]}}</h4>
    <p>{{ price2 }} 만원</p>
    <button @click="increase(1)">허위매물신고</button> <span>신고수 : {{신고수[1]}}</span>
  </div>
  <div>
    <h4>{{products[2]}}</h4>
    <p>{{ price2 }} 만원</p>
  </div>
</template>

<script>
// 데이터 바인딩하는 이유 
// 1. 하드코딩하면 변경어려우니깐 
// 2. 실시간 렌더링 기능을 이용하기 위해서 -> 웹앱!!
// 자주 변할 데이터들은 데이터로 보관하고 HTML에 꽂아넣기 {{}}



export default{
  name: 'App',
  data(){
    return{
      price1 : 60,
      price2 : 70,
      스타일 : 'color : blue',
      메뉴들 : ['Home', 'Shop', 'About'],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      신고수 : [0,0,0],
    }
  },
  methods: {
    increase(i){ 
      this.신고수[i] += 1;
    }
  },
  components: {
   
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.menu{
  background: darkblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}
</style>
