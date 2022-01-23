<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
  <!--  <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <Calc />
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue' //
import Calc from "@/components/Calc.vue"

export default {
  name: 'Home',
  components: {
    Calc
  }
}
</script>

<style lang="scss" scoped>

</style>
