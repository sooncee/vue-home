<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <header>
    <div class="menu">
      <a href="" v-for="left in menus" :key="left">{{left}}</a>
      <!-- <a href="" v-for="(left,i) in menus" :key="i">{{i}}</a> -->
    </div>
  </header>
  <div class="body-menu">
    <!-- <div v-for="ii in titles" :key="ii">
      
        <h4>{{ii}}</h4>
        <p>10000</p>
      
    </div>
    <div v-for="(j,i) in 3" :key="i">
      
        <h4>{{titles[i]}}</h4>
        <p>10000</p>
      
    </div> -->
    <div>
      <button @click="count++">허위매물신고</button> <span>신고수 : {{count}}</span>
    </div>
  </div>
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data(){
    return{
      count:0,
      price1 : 600000,
      price2 : 700000,
      titles : ['역삼동 원룸','천호동 원룸','마포구 원룸',],
      price :[500000,600000,700000],
      menus : ['home','shop','about']
    }
  },
  components: {
    // HelloWorld
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
}
.menu{
  background: darkslateblue;
  padding: 15px;
  display: flex;
  align-content: center;
  justify-content: space-around;
}
.menu a{
  color: #fff;
}
</style>
