<template>
    <div class="black-bg" v-if="modalCheck == true">
      <div class="white-bg">
         <img :src="posts[modalNumber].image" alt="">
         <h4>{{ posts[modalNumber].title }}</h4>
        <p>{{posts[modalNumber].content}}</p>
        
        <!-- 수량 <input @input="month = $event.target.value"> -->
        <input type="text" v-model.number="month">
        <!-- <input type="range" min="1" max="12" v-model="month"> -->
        <!-- <select v-model="month">
         <option value="1">1개월</option>
         <option value="2">2개월</option>
         <option value="3">3개월</option>
        </select> -->
        <!-- <input type="checkbox" v-model="month"> -->
        <p>{{ month }}개월 선택함 {{posts[modalNumber].price * month}}</p>
         <button @click="$emit('closeModal')">닫기</button>
      </div>
    </div>
</template>

<script>
export default {
   name : 'Modal',
   data(){
      return {
         month : 1,
      };
   },
   watch: {
      month(a,b){
         if(isNaN(a) === true){
            alert("nono")
            this.month = b
         }
      }
   },
   props: {
      posts : Object,
      modalNumber : Number,
      modalCheck : Boolean,
   }
}
</script>

<style>

</style>