<template>
  <div class="discount">
    DIscount {{sale}}% 컴포넌트요
  </div>
</template>

<script>

export default {
  data() {
    return {
      sale: 30
    }
  },
  mounted() {
    setInterval(() => {
        if(this.sale > 0){
          this.sale = this.sale - 1
        }
      }, 100);
  },
}
</script>

<style>

</style>