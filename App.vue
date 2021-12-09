<template>

  <div class="black-bg" v-if="모달창오픈 == true"> <!-- v-if="조건식" => 조건식이 참일 때만 HTML 보여줌 -->
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세페이지 내용</p>
      <button @click="모달창오픈 = false">Close</button>
    </div>
  </div>

  <div class="menu">
    <!-- 1. 자료안의 데이터 갯수만큼 반복됨
    2. 작명한 변수는 데이터안의 자료가 됨 
    
    :key=""의 용도 => 반복문 돌린 요소를 컴퓨터가 구분하기 위해씀 -->
    <a v-for="i in menus" :key="i">{{ i }}</a>
  </div>

  <div>
    <img :src="원룸들[0].image" class="room-img">
    <h4 @click="모달창오픈 = true">{{ 원룸들[0].title }}</h4>
    <p>{{ 원룸들[0].price }}원</p>
    <button v-on:click="신고_수[0]++">허위매물 신고</button> 
    <span>신고 수: {{ 신고_수[0] }}</span>
  </div>

  <div>
    <img :src="원룸들[1].image" class="room-img">
    <h4 @click="모달창오픈 = true">{{ 원룸들[1].title }}</h4>
    <p>{{ 원룸들[1].price }}원</p>
    <button v-on:click="신고_수[1]++">허위매물 신고</button> 
    <span>신고 수: {{ 신고_수[1] }}</span>
  </div>

  <div>
    <img :src="원룸들[2].image" class="room-img">
    <h4 @click="모달창오픈 = true">{{ 원룸들[2].title }}</h4>
    <p>{{ 원룸들[2].price }}원</p>
    <button v-on:click="신고_수[2]++">허위매물 신고</button> 
    <span>신고 수: {{ 신고_수[2] }}</span>
  </div>
  
  <div>
    <img :src="원룸들[3].image" class="room-img">
    <h4 @click="모달창오픈 = true">{{ 원룸들[3].title }}</h4>
    <p>{{ 원룸들[3].price }}원</p>
    <button v-on:click="신고_수[3]++">허위매물 신고</button> 
    <span>신고 수: {{ 신고_수[3] }}</span>
  </div>

  <div>
    <img :src="원룸들[4].image" class="room-img">
    <h4 @click="모달창오픈 = true">{{ 원룸들[4].title }}</h4>
    <p>{{ 원룸들[4].price }}원</p>
    <button v-on:click="신고_수[4]++">허위매물 신고</button> 
    <span>신고 수: {{ 신고_수[4] }}</span>
  </div>

  <div>
    <img :src="원룸들[5].image" class="room-img">
    <h4 @click="모달창오픈 = true">{{ 원룸들[5].title }}</h4>
    <p>{{ 원룸들[0].price }}원</p>
    <button v-on:click="신고_수[5]++">허위매물 신고</button> 
    <span>신고 수: {{ 신고_수[5] }}</span>
  </div>

</template>

<script>
import data from './post.js';

// 데이터 바인딩 하는이유
// 1. HTML에 하드코딩 해놓으면 나중에 변경 어려움
// 2. Vue의 실시간 자동 렌더링 쓸때
export default {
  name: 'App',
  data(){
    return {
      원룸들: data,
      모달창오픈 : false,
      신고_수: [0, 0, 0, 0, 0, 0],
      menus: ['Home', 'Shop', 'About'],
      products : ['역삼동 원룸', '천호동 원룸', '마포구 원룸'],
    }
  },

  // 동적인 UI만드는 법:
  // 1. UI의 현재 상태를 데이터로 저장해둠
  // 2. 데이터에 따라 UI가 어떻게 보일지 작성

  components: { 
  }
}

</script>

<style>
body {
  margin: 0;
}

div{
  box-sizing: border-box;
}

.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}

.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}

.room-img {
  width: 100%;
  margin-top: 40px;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}




#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
