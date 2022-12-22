<template>
  
  <div class="item">
      <picture>
        <img :src="prdId.image" alt="">
        <p>{{ prdId.content }}</p>
        <p>{{prdId.price }}</p>
      </picture>
    </div>

    <!-- <div v-for="(a,b) in post" :key="b" class="item">
      <picture>
        <img :src="a.image" alt="">
        <h4 v-on:click="modalCheck = true; modalNumber = b">{{a.title}}</h4>
        <p>{{ a.content }}</p>
        <p>{{a.price }}</p>
        <div>
          {{ a.count }}
          <button @click="a.count++">추천</button>          
        </div> 
      </picture>
    </div> -->

</template>

<script>
export default {
   props : {
      prdId : Object, 
   }
}
</script>

<style>

</style>