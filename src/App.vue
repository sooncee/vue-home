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

    <div v-for="(a,b) in post" :key="b" class="item">
      <picture>
        <img :src="post[b].image" alt="">
        <h4 v-on:click="modalCheck = true; modalNumber = b">{{post[b].title}}</h4>
        <p>{{ post[b].content }}</p>
        <p>{{post[b].price }}</p>
        <div>
          {{ post[b].count }}
          <button @click="post[b].count++">추천</button>          
        </div> 
      </picture>
    </div>
    
    <div class="black-bg" v-if="modalCheck === true">
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
    </div>
  </div>
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
</template>

<script>
  // import HelloWorld from './components/HelloWorld.vue' 
  import worldBanner from './components/worldBanner.vue' 
  import post from './post.js';

  export default {
    name: "App",
    data() {
      return {
        modalCheck: false,
        modalNumber: 0,
        images: ["room0", "room1", "room2"],
        price1: 600000,
        price2: 700000,
        titles: ["역삼동 원룸", "천호동 원룸", "마포구 원룸"],
        price: [500000, 600000, 700000],
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