<template>
<section class="container">
    <!-- 
      gender: "Male"
      id: 1
      image: "https://rickandmortyapi.com/api/character/avatar/1.jpeg"
      name: "Rick Sanchez"
      origin: "Earth (C-137)"
      species: "Human"
      status: "Alive"
      type: "Human" 
    -->
    <loader-component v-if="loading" />
    <div class="row">
      <div v-for="character in characterList" :key="character.id" class="col-6 col-md-4 col-lg-3">
        <card-component :item="character" />
      </div>
    </div>
    <footer-component :len="characterList.length" v-if="!loading" />

</section>
 
</template>

<script>
import LoaderComponent from './LoaderComponent.vue';
import CardComponent from './CardComponent.vue';
import FooterComponent from './FooterComponent.vue';
import axios from 'axios';

export default {
  name: 'MainComponent',
  components: {
    LoaderComponent,
    CardComponent,
    FooterComponent
    
  },
  data(){
    return {
      characterList: [],
      apiPath:'https://api.sampleapis.com/rickandmorty/',
      loading: false,
    }
  },
  mounted(){
    this.loading = true;
    axios.get(this.apiPath + 'characters').then((res)=>{
      console.log(res)
      this.characterList = [...res.data];
      this.loading = false;
    }).catch((error)=> {
      console.log(error)
      this.loading = false;
    });
  }
}
</script>

<style lang="scss" scoped>

</style>