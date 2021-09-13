<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <Home 
      :msg="msg"
    />
  </div>
</template>

<script>
import Home from '@/components/HomeComp.vue'

export default {
  name: 'HomeView',
  components: {
    Home
  },
  data() {
    return {
      msg: 'This is my custom TODO app! Enjoy'
    }
  },
}
</script>
