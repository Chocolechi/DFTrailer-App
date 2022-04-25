<template>
  <div class="container">
    <HeaderApp />
    <MainInfo />
    <TrailerList />
    <FooterPage />
  </div>
</template>

<script>
// @ is an alias to /src
import HeaderApp from '@/components/Header-App.vue'
import MainInfo from '@/components/Main-Info.vue'
import TrailerList from '@/components/Trailer-List.vue'
import FooterPage from '@/components/Footer-Page.vue'

export default {
  name: 'HomeView',
  components: {
    HeaderApp,
    MainInfo,
    TrailerList,
    FooterPage,
  }
}
</script>
