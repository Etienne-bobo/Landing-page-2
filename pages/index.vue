<template>
  <div>
    <nav-bar />
    <Header />
    <Content />
    <Footer />
  </div>
</template>

<script>
import NavBar from '~/layouts/navBar.vue'
import Header from '~/components/Home/Header'
import Content from '~/components/Home/Content'
import Footer from '~/layouts/footer'
export default {
  components: {
    NavBar,
    Header,
    Content,
    Footer
  }
}
</script>

<style>

</style>
