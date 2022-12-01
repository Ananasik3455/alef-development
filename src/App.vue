<template>
  <div class="container">
    <Header/>
    <Content/>
    <Footer/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Content from './components/Content'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  data() {
    return {
      modalVisible: false
    }
  },
  components: {
    Header,
    Content,
    Footer,
  }
}
</script>

<style>
  @import './assets/style/style.css'
</style>
