<template>
  <div id="app">
    <MainHeader @search="searchAlbum" ></MainHeader>
    <MainContent :search="searchGenre"  />
  </div>
</template>

<script>
import MainHeader from './components/MainHeader.vue';
import MainContent from './components/MainContent.vue';


export default {
  name: 'App',
  components: {
    MainHeader,
    MainContent,

},
data(){
  return {
    searchGenre: ''
  }
},
  methods:{
    searchAlbum(searchG){
      this.searchGenre = searchG
      console.log(" Genere selezionato : ", searchG)

    }
  }
}
</script>

<style lang="scss">
  @import './var.scss';
  @import './index.scss';
  #app{
    background-color: $bg-darkblue;
  }
</style>
