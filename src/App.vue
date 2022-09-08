<template>
  <div id="app">
    <MainHeader @search="searchAlbum" @searchName="searchAlbumF" @searchArtist="searchAlbumArtist" @searchYear="searchAlbumYear" ></MainHeader>
    <MainContent :search="searchGenre" :searchAlbum="albumNameText" :searchArtist="albumArtistText" :searchYear="albumYearText"  />
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
    searchGenre: '',
    albumNameText:'',
    albumArtistText:'',
    albumYearText:'',
  }
},
  methods:{
    searchAlbum(searchG){
      this.searchGenre = searchG
      console.log(" Genere selezionato : ", searchG)

    },
    searchAlbumF(searchA){
      this.albumNameText = searchA
      console.log("Nome dell'album :", searchA)
    },
    searchAlbumArtist(searchArt){
      this.albumArtistText = searchArt
      console.log("Autore dell'album :", searchArt)
    },
    searchAlbumYear(searchY){
      this.albumYearText = searchY
      console.log("Annodell'album :", searchY)
    },
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
