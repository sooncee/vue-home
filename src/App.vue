<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <header>
    <div class="menu">
      <a href="" v-for="left in menus" :key="left">{{ left }}</a>
    </div>
  </header>
  <div class="body-menu">
   <!-- <div class="start" :class="{end : modalCheck}"> -->
    <transition name="fade">
      <Modal @closeModal="modalCheck = false" v-bind:posts="post" :modalCheck="modalCheck" :modalNumber="modalNumber" />
    </transition>
   <!-- </div> -->

   <!-- <transition name="fade"> -->
     <hey msg="heyy"/>
     <!-- </transition> -->

      <Card @openModal="modalCheck = true; modalNumber = $event" :prdId="post[b]" v-for="(a,b) in post" :key="b" />

    

  </div>
</template>

<script>
  import worldBanner from './components/worldBanner.vue' 
  import post from './post.js';
  import Modal from './components/modal.vue'
  import card from './components/card.vue'

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
      Modal,
      Card:card,
    },
  };
</script>

<style>
  * {
    box-sizing: border-box;
  }

  .fade-enter-from{
    opacity: 0;
  }
  .fade-enter-active{
    transition: all .3s ease-in-out;
  }
  .fade-enter-to{
    opacity: 1;
  }

  .fade-leave-from{
    opacity: 1;
  }
  .fade-leave-active{
    transition: all .3s ease-in-out;
  }
  .fade-leave-to{
    opacity: 0;
  }

  .start{
    opacity: 0;
    transition: all .3s ease-in-out;
  }
  .end{
    opacity: 1;
  }

  .discount{
    padding:40px;
    background: #f9f9f9;
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