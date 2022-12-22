<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <header>
    <div class="menu">
      <a href="" v-for="left in menus" :key="left">{{ left }}</a>
    </div>
  </header>
  <div class="body-menu">
    <!-- <div v-for="(aa, bb) in titles" :key="bb">
      <img src="./assets/room0.jpg" alt="" />
      <h4 v-on:click="modalCheck = true">{{ titles[bb] }}</h4>
      <p>{{ price[bb] }}</p>
      <button v-on:click="count[bb]++">허위매몰신고</button>
      <span>신고 수 {{ count[bb] }}</span>
    </div> -->

    <hey msg="heyy"/>

    <!-- <card :prdId="post[0]"/> -->
    <card :prdId="cb" v-for="(cb,ii) in post" :key ="ii"/>
    <card :prdId="post[ii]" v-for="(cb,ii) in post" :key ="ii"/>

    
    
    <!-- modal -->
    <!-- <div class="black-bg" v-if="modalCheck === true">
      <div class="white-bg">
        <h4>{{ post[modalNumber].title }}</h4>
        <img :src="post[modalNumber].image" alt="">
        <p>{{post[modalNumber].content}}</p>
        <p>{{post[modalNumber].price}}</p>
        <div>
          {{ post[modalNumber].count }}
          <button @click="post[modalNumber].count++">추천</button>    
        </div>
        <div>
          <button @:click="modalCheck = false">닫기</button>
        </div>
      </div>
    </div> -->

  </div>
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
</template>

<script>
  // import HelloWorld from './components/HelloWorld.vue' 
  import worldBanner from './components/worldBanner.vue' 
  import card from './components/card.vue'
  import post from './post.js';
  

  export default {
    name: "App",
    data() {
      return {
        modalCheck: false,
        modalNumber: 0,
        menus: ["home", "shop", "about"],
        post : post,
      };
    },
    methods: {
      increase() {
        // this 내 오브젝트를 뜻함
        this.count++;
      },
    },
    components: {
      hey : worldBanner,
      card,
    },
  };
</script>

<style>
  * {
    box-sizing: border-box;
  }

  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    max-width: 420px;
    width: 100%;
    margin: auto;
  }

  .item{
    margin-bottom: 40px;
  }

  .menu {
    background: darkslateblue;
    padding: 15px;
    display: flex;
    align-content: center;
    justify-content: space-around;
  }

  .menu a {
    color: #fff;
  }

  .black-bg {
    max-width: 420px;
    width: 100%;
    height: 100%;
    position: fixed;
    top: 0;
    padding: 20px;
    background: rgba(0, 0, 0, 0.5);
  }

  .white-bg {
    width: 100%;
    padding: 20px;
    background: #fff;
    border-radius: 20px;
  }

  img{
    width: 100%;
  }
</style>