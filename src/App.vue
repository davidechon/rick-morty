<template>
  <div id="app">
    <HeaderComponent :title="titolo"/>
    <div>
    <MainComponent />
    <CardComponent />
    </div>
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue'; 
import MainComponent from './components/MainComponent.vue'
import FooterComponent from './components/FooterComponent.vue'

export default {
  name: 'App',
  components: {
    HeaderComponent,
    MainComponent,
    FooterComponent,
  },
  data(){
    return {
      titolo: "Rick and Morty",
    }
  }
}
</script>

<style lang="scss">
@import "@/assets/style/general.scss";
</style>
