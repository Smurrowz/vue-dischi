<template>
  <main>
    <div class="my-container">
      <LoaderContent :content="listAlbums" />
      <AlbumCard :albums="filteredAlbums" />
      

    </div>
  </main>
</template>
<script>
import AlbumCard from './AlbumCard.vue';
import axios from "axios";
import LoaderContent from './LoaderContent.vue';

export default {
  name: "MainContent",
  components: { AlbumCard, LoaderContent },
  props:{
    search: {
      type: String,
      default: ''
    },
    searchAlbum :{
      type: String,
      default: ''
    },
    searchArtist :{
      type: String,
      default: ''
    },
    searchYear :{
      type: String,
      default: ''
    },
    
  },
  data() {
    return {
      listAlbums: [],
     
    }
  },
  computed:{
    filteredAlbums(){
      return this.listAlbums.filter((album) => {
        
        const genre = album.genre
        const option = this.search
        const title = album.title.toLowerCase()
        const titleInput = this.searchAlbum.toLowerCase()
        const artist = album.author.toLowerCase()
        const artistInput = this.searchArtist.toLowerCase()
        const year = album.year
        const yearInput = this.searchYear
        
        if(genre.includes(option) && title.includes(titleInput) && artist.includes(artistInput) && year.includes(yearInput)){
          return true
        }else{
          return false
        }
      })        
    }
  },
  created() {
    axios
      .get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((res) => {
        this.listAlbums = res.data.response;
      })
  }
}
</script>
<style scoped lang="scss">
@import '../var.scss';
@import '../index.scss';

main {
  padding: 70px 0;
  height: 100vh;
}
</style>