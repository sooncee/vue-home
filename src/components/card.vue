<template>
  
  <div class="item">
      <picture>
        <img :src="prdId.image" alt="">
        <h4 @click="$emit('openModal', prdId.id)">{{ prdId.content }}</h4>
        <p>{{prdId.price }}</p>
      </picture>
    </div>

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