<template>
  <div class="container">
    <Header />
    <Main>
      <CategoriesList :categories="categories" />
    </Main>
    <Footer />
  </div>
</template>

<script>
  import {mapState} from 'vuex'

  import Header from '../layouts/header'
  import Main from '../layouts/main'
  import Footer from '../layouts/footer'
  import CategoriesList from '../components/common/CategoriesList'

  export default {
    components: {
      Header,
      Main,
      Footer,
      CategoriesList
    },
    async asyncData ({app, route, params, error, store}) {
      try {
        await store.dispatch('getCategoriesList')
      } catch (e) {
        console.log(e)
        return error({
          statusCode: 404,
          message: 'Categories not founded'
        })
      }
    },
    computed: {
      ...mapState({
        categories: 'categoriesList'
      })
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
