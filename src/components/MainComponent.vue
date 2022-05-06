<template>
<div>
  <!-- gender: (…)
      id: (…)
      image: (…)
      name: (…)
      origin: (…)
      species: (…)
      status: (…)
      type: (…) -->
  <div v-for="(item, index) in characterList" :key="index">
    id {{item.id}} - name {{item.name}} - status {{item.status}} - type {{item.type}} - species {{item.species}} <img :src="item.image" alt="">
  </div>
</div>
 
</template>

<script>
import axios from 'axios';

export default {
  name: 'MainComponent',
  data(){
    return {
      characterList: [],
      apiPath:'https://api.sampleapis.com/rickandmorty/',
    }
  },
  mounted(){
    axios.get(this.apiPath + 'characters').then((res)=>{
      console.log(res)
      this.characterList = res.data;
    });
  }
}
</script>

<style lang="scss" scoped>

</style>