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
    } 
    
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
        // const title = album.title
        // const artist = album.author
        // const year = parseInt(album.year)
        
        if(genre.includes(option)){
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