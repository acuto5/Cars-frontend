<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    {{test}}
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
    cars: [1, 2, 3],
    data() {
        return {
            test: "testas"
        }
    },created(){
        console.log(this.cars)
    },
  name: 'home',
  components: {
    HelloWorld
  }
}
</script>
