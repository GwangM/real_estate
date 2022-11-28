<template>
  <div class="black-bg" v-if="modalOpen == true">
    <div class= "white-bg">
      <h4>상세페이지</h4>
        <p>페이지 내용</p>
        <button @click="modalOpen=false">닫기</button>
    </div>
  </div>


  <div class="menu">
    <a v-for="(a,i) in menus" :key="i">{{a}}</a>
  </div>

  <div>
    <img src="./assets/room1.jpg" class="room-img">
    <h4 @click="modalOpen=true">{{products[0]}}</h4>
    <p>50 만원</p>
    <button v-on:click="reports[0]++">허위매물신고</button> <span>신고수 : {{reports[0]}}</span>
  </div>
  <div>
    <img src="./assets/room2.jpg" class="room-img">
    <h4 @click="modalOpen=true">{{products[1]}}</h4>
    <p>60 만원</p>
    <button @click="reports[1]++">허위매물신고</button>
    <span>신고수 : {{reports[1]}}</span>
  </div>
  <div>
    <img src="./assets/room3.jpg" class="room-img">
    <h4 @click="modalOpen=true">{{products[2]}}</h4>
    <p>70 만원</p>
    <button @click="reports[2]++">허위매물신고</button>
    <span>신고수 : {{reports[2]}}</span>
  </div> 

</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      modalOpen: false,
      reports: [0,0,0],
      menus:['Home', 'Shop', 'About'],
      products:['서천동원룸','기흥구원룸','우산동원룸'],
    }
  },
  methods: {
    increase(){
      this.reports++;
    }
  },
  components: {
  }
}
</script>

<style>
body{
  margin:0
}
div{
  box-sizing: border-box;
}
button{
  margin-right:5px;
}
.black-bg{
  width:100%;height:100%;
  background: rgba(0,0,0,0,5);
  position: fixed; padding:20px;
}
.white-bg{
  width:100%;background: white;
  border-radius: 8px;
  padding: 20px;
}
.room-img{
  width:100%;
  margin-top: 40px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu{
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a{
  color: white;
  padding: 10px;
}
</style>
