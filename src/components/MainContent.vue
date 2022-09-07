<template>
  <main>
    <div class="my-container">

      <AlbumCard :albums="listAlbums" />

    </div>
  </main>
</template>
<script>
import AlbumCard from './AlbumCard.vue';
import axios from "axios";

export default {
  name: "MainContent",
  components: { AlbumCard },
  data() {
    return {
      listAlbums: [],
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
}
</style>