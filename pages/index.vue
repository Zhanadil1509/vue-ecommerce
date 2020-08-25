<template>
  <div class="container">
    <Header />
    <Main />
    <Footer />
  </div>
</template>

<script>
  import Header from '../layouts/header'
  import Main from '../layouts/main'
  import Footer from '../layouts/footer'

  export default {
  components: {
    Header,
    Main,
    Footer
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
}
</style>
